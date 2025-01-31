---
title: "Blockchain tech opportunities in the Web-of-Trust"
permalink: rwot1-sf/topics-and-advance-readings/blockchain-opportunities/
sidebar:
  - title: RWoT1-SF
    nav: rwot1
  - title: "Rebooting the Web of Trust"
    nav: rwotnav
authors:
  - "Peter Todd"
gitlink: "https://github.com/WebOfTrustInfo/rwot1-sf/blob/master/topics-and-advance-readings/blockchain-opportunities.txt"

---

*by Peter Todd*

Before we ask how "blockchain" tech can improve the web-of-trust, lets first
look at what they have in common. We'll use the example of OpenPGP, the most
common web-of-trust technology in use by far, and Bitcoin, the most succesful
blockchain technology.

Both technologies rely on chains of provable statements. In Bitcoin if Alice
pays Bob who pays Charlie who pays David we have a transaction chain:

    tx-Alice <- tx-Bob <- tx-Charlie <- tx-David

This is not unlike a trust chain of signed keys that might give David some
assurance that a message from Alice really is from Alice, where David has
signed Charlie's key who has signed Bob's who has signed Alice's.

    Alice <- Bob <- Charlie <- David

In both cases we're dealing with cryptographically signed data packets, whose
existance proves certain facts; in both cases we have an implementation of a
flood-fill network to move these facts to all who might want to know them - the
PGP key servers and the Bitcoin P2P nodes.

What different is the need for consensus. It's perfectly OK if there exist
multiple trust signatures from Bob to Alice; it's totally OK if David and Dan
use different trust paths to verify a signature from Alice, and in fact, the
ability to do so may be useful if Bob doesn't want Dan to know about his
relationship with Alice. In Bitcoin however, if Bob can spend the money Alice
sent him twice, this is a disaster.


Single Use Seals
----------------

In short, we need an anti-doublespend mechanism. Without getting into the
details of how Bitcoin achieves this, in short it does, leading to the property
that a given transaction output can be spent exactly once. We can model this
capability as a Single Use Seal(1) - a globally unique seal that can be closed
over a digest exactly once, resulting in a witness. An implementation with
Bitcoin uses transaction outputs as the seals; to close a seal you spend the
transaction output appropriately. The spending transaction is witness to the
fact that the seal is now closed and is now irrovocably committed to that
digest.

A second type of witness is also possible in principle: proof that a seal has
not been closed, as of a particular time. Bitcoin currently lacks a (compact)
way to cryptographic prove this, but may in the future if (U)TXO commitments
are implemented; full nodes can verify an output has not been spent by
examining their UTXO set.


Key revocation and rotation with Single Use Seals
-------------------------------------------------

While OpenPGP currently supports key revocation there is no way to guarantee
receipt of a revocation - keyservers can censor revocations to prevent
verifiers from learning that a key has been compromised. With the single use
seal mechanism however we can guarantee revocation reception in two ways:

1) If the underlying SUS implementation can prove a seal is open, we can define
   revocation to be the act of closing a specified seal.

2) Failing that, we can use key expiration, with continuing key validity being
   defined as the appropriate seal for that time period has been closed over a
   signed message proving the key is still valid.

We can also support key rotation analogously, either by proving a key has not
been rotated, or by rotation on a fixed schedule driven by expiry dates. (e.g.
through a globally unique mapping(2)) In both cases the single-use-seal
mechanism guarantees that all verifiers are using the correct key.


Timestamps
----------

As a side effect of the difficulty adjustment algorithm, Bitcoin blocks have a
reasonably accurate time field in them that can be used for timestamping.
Currently OpenPGP has no good mechanism for proving that signatures were
created in the past. This causes a number of practical problems, first and
foremost being that once a key is revoked - particularly due to a compromise -
it becomes difficult to impossible to verify signatures made with that key.
Timestamping signatures would allow such signatures to be succesfully verified
by proving that they were created prior to revocation.


References
----------

1) https://github.com/proofchains/python-proofchains/blob/master/proofchains/core/uniquebits/singleuseseal.py

2) https://github.com/proofchains/python-proofchains/blob/master/proofchains/core/uniquebits/gumap.py
