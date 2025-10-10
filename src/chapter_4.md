# Consensus and Global State

What you might have realized so far in our discussion of AO's architecutre is
that there has been no mention of "blocks", or adding blocks to a "blockchain".

This does happen at the *Arweave* level, but no blocks are being produced by the
AO network itself.

Looking at the previous chapter, you may still have some unanswered questions.
The largest one likely being "*where is consensus?!?!?!?!?!?*"

In this chapter we'll explore the security and consensus model of AO in more detail, 
first taking a look at the state level.

## The state layer

Consensus on AO does not exist the same way as it does on Ethereum (or even
Arweave, for that matter). 

It provides different security mechanisms based on different needs, but
ultimately, Arweave acts as the **immutable state layer** from which computation
uses as a source of truth. 

As mentioned in the previous chapter, schedulers order and store messages on Arweave,
and AO nodes perform computation based on this message log on Arweave.

This means at the state layer, consensus is solved. Once a set of messages are
on Arweave they are immutable and tamper-proof: in other words, anyone can read
from this log of messages stored on Arweave and re-construct the state of an AO
process.

Users could even run their own AO node and compute this for themselves - no need
to even request computation from a node or a consortium of nodes.

From this persective, AO essentially inherits the security of Arweave for the 
**storing and reading of message data**. 

Where consensus is instead important is the layer on top of this - computation, 
and the layer previous (scheduling).

## Ensuring computational correctness

With all of the information given, this raises the question: 

How do you ensure nodes return truthful results to a user?

This ultimately depends on the level of insurance for "trust" that end users or
applications require. 

Users, for example, could run their own AO node and compute the results from
Arweave themselves. These provides a high level of verification. 

Most users, however, do not end up running their own node. This means that AO
nodes will typically compute results for users.

Once AO has fully converted to mainnet, these nodes will make use of economic
incentives and staking in order to incentivize the returning of correct results 
to users.

The fact that the state is implied and re-constructable from Arweave by
anyone also  means that nodes are heavily disincentivized to tamper with the result.

If an AO node decided to return an unthruthful result - the "truth" is on Arweave.
It only will affect the frontend, for example the displaying of an incorrect balance,
which does not reflect the actual balance onchain. They cannot affect the actual
state of a process.

This leaves one part of consensus to be answered:

How do you ensure that Scheduler Units order transactions in a fair, and
tamper-proof way?

We will not cover that in the scope of this bok at the moment.
