---
title: "Principle of Relativity for WoT"
permalink: rwot1-sf/topics-and-advance-readings/Principle-of-Relativity-for-WoT/
sidebar:
  - title: RWoT1-SF
    nav: rwot1
  - title: "Rebooting the Web of Trust"
    nav: rwotnav
authors:
  - "David Strayhorn"
gitlink: "https://github.com/WebOfTrustInfo/rwot1-sf/blob/a8c6058e56bef5cea62162585c1e0bf9f795521b/Principle-of-Relativity-for-WoT.md"

--- 

**_by David Strayhorn_**

## Abstract

By way of an analogy to Einstein's theory of relativity, I propose a principle of relativity for reputation in the context of the web of trust (WoT). This principle states that reputation can only be properly understood relative to a specific end-user. In other words, reputation is in the eye of the beholder. By this principle, we should shift focus from global reputation (e.g. Bob's trust score in absolute terms) to local reputation (e.g., Alice's evaluation of Bob's trustworthiness). Indeed, any attempt to construct WoT in a manner that enables the calculation of global reputation necessarily exacts a cost to privacy and in so doing will be detrimental to the overall utility of the WoT.

## Body

Most widely used systems for reputation and ratings calculate a single composite score out of a large number of individually submitted ratings. Examples include 1-5 star rating systems on Amazon or Yelp, feedback on eBay, or karma on reddit. These scores are global in the sense that the same score is viewed by all users. I would like to put forth the argument that global scores must be abandoned and replaced by local scoring systems, where composite scores depend not only on the user or entity being observed, but also on the user doing the observing. I call this the principle of relativity for ratings and reputation. Violation of this principle necessarily comes at the cost of privacy, because calculation of a global score assumes from the outset that certain pieces of data, such as individual ratings, must be visible to everybody if they are to have any meaningful existence at all.

The name principle of relativity is meant as an analogy to Einstein’s principle of relativity. In Einstein’s theory, distance and time are not global invariants. That means that there is no such thing as the distance (or time) between two events in the absolute sense; distance (or time) only has meaning when the observer frame of reference is specified, and no frame is priv- ileged over any other. I submit that reputation, like distance or time, is not a global invariant. There is no such thing as reputation in the global or absolute sense; reputation only has meaning when referenced to a specific (local) observer (i.e. a node in the network or a specific user).

Consider the example of attempting to calculate a ”Trust Score” for highly controversial people, like Putin or George Bush or anyone with political power. Some people would trust him a lot; others not at all. So what would a global Trust Score tell us? How would we even define it? And what use would it be? Sure, we could talk about the average, but there are many ways to define that (average over all people in the world? average over a subset? give more weight to some people than others? median? mean?), and it’s not clear that any one of them carries any special truth or utility. (They probably both get a 3 out of 5. So what?) It is only when the calculation is tailored to my unique perspective that the number starts to become useful to me. The more I can tailor it, the more useful I can make it.

This principle states that we must abandon the desire to devise global composite reputation variables like a global trust score. The practice of doing so is an unfortunate side effect of having granted stewardship of our personal data to large centralized entities, where there is a privileged frame of reference: that of the centralized entity. It may take some time to shed ourselves of this way of thinking. Until we do so, we will continue to spin our wheels in frustration trying to devise that which does not exist, a one-size-fits-everybody’s-needs set of trust scores and other measures.

It is important to consider what this principle says about a WoT network topology: any given node (user) should be assumed to have only an incomplete view of the global topology of the network. It is tempting to try to violate this principle while designing a reputation system in which trust (or some other quantitiy) propagates through the network (transitivity). However, any attempt to require that nodes and connections between them must be publicly visible will of necessity be unsuccessful in a p2p network where nodes (individuals) are truly the stewards of their data (and may not wish their connections to be public knowledge), and is ill-conceived.

We must emphatically abandon the current, naive practice of assuming (or hoping) that people will freely submit accurate, informative, honest ratings for public consumption because it’s fun or because we tell them that it’s for the greater good. Individuals should only be expected to yield personal data (including but not limited to the identity of nodes connected to them in some way) once they have been properly incentivized. How to incentivize must therefore become a major focus. Individuals could for example provide access to their ratings data, or information regarding local network topology, to other nodes in exchange for a microfee, or in exchange for another node’s knowledge of its local topology. Once the end user is recognized as having complete ownership of his or her data, once the principle of relativity is recognized in the design of WoT networks, and once people are properly incentivized to divulge their created content such as ratings, we will start to see WoT become truly useful. But not before.
