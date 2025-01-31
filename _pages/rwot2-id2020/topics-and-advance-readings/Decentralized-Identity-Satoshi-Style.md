---
title: "Decentralized Identity Satoshi Style"
authors:
  - "Darrell Duane"
gitlink: "https://github.com/WebOfTrustInfo/rwot2-id2020/blob/master/topics-and-advance-readings/Decentralized-Identity-Satoshi-Style"

---

Decentralized Identity Satoshi Style
Darrell Duane
darrell@idi.io

Bitcoin and other new crypto-currencies have brought many new possibilities for how value is exchanged between individuals.  
These currencies, utilizing blockchain technology allow for anyone with an internet connection anywhere in the world to 
send an arbitrary measure of value to anyone else with an internet connection anywhere in the world with a small fee, rapidly, 
and unconditionally, without risk of chargeback.  Further, these transactions are unmediated by any third party; to permanently 
stop them, you'd have to shut down the entire internet, an unlikely proposition.  At present most of these coins offer only 
pseudonymous transfers, but coins using Coin-Join and Zero Knowledge Proof technology offer possibilities for more anonymity 
and minimal traceability for transactions for those who desire it.   The Blockchain, by combining peer-to-peer network that 
solves the byzantine  generals problem and the double-spending problem, secures a publicly readable, distributed ledger to 
maintain the balances that each public/private key-pair has management rights over.
Many are now asking how we can extend the use of the Blockchain to solve the myriad of problems within the identity space. 
However, I haven't seen any approach yet which  puts the INDIVIDUAL in total control of their identity the way that Bitcoin 
puts the individual in total control of their financial transactions.  When you use a Bitcoin wallet that is a native 
application, you are in a way your own bank, from the point of being a money transfer agent.  The user is broadcasting 
directly onto the peer-to-peer network, and assuming unbiased miners, the user is the money transmitter.  Money Transmitters 
are highly regulated businesses, and so now there is much legislation that has been recently put into place or under 
consideration in various jurisdictions regarding the use of crypto currencies.  
Identity is fundamentally different from financial transactions in that is inherently vulnerable to the “double spend” problem.  
PII can potentially be transmitted with the ease that any other data is transferred from one entity to another.  
Some transfers may be warranted, others may be due to a hack.  Unlike financial ledgers, where the transfer of value 
from one party to another is permanent, identity attributes, or other characterizations cannot be unseen.  Access may 
be able to be revoked, but the fact that access has been revoked or granted cannot but expunged.   

While contracts and laws can be written regarding how second and third parties handle information, the potential 
for data breaches, nefarious actors, or other compromises and even lack of understanding of contacts can lead to 
disclosure of identity compromising information.  How can we apply the same standards of protection that Bitcoin
provides to financial transactions to identity transactions?!  What would a decentralized identity management system look like?

1.  Does not rely on centralized repositories of information.

2.  Does not rely on centralized actors to manage access.

3. Is not editable by anyone except the owners of the private key(s) that manage it.  (Multi-sig would get used a lot here)

4.  Allows individuals to create their own identity profiles, as many as they have identity relationships to provide anonymity or isolation of identities.

5.  Has a method to easily prevent sybil attack for the identity applications that require it.  This system would not be about sybil detection and resolution, but would be about preventing any sybil attacks in the first place. There is much work going on in this field.

6. Prevent transfers of access/attributes in cases where the owner required them to be assigned only to the individual, and on the flip side, allow distinct transfers of access or tokens to others that doesn’t allow for double spending as required.  

7. Allow for the use of biometrics as needed, with configurable thresholds for the desired risk portfolio of an identity application.

This is just a brief introduction to the challenges and possibilities at hand when we treat identity problems in the same manner that Satoshi treated the exchange of value problem. 
