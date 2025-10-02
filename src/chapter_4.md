# Consensus and Global State

What you might have realized so far in our discussion of AO's architecutre is
that there has been no mention of "blocks", or adding blocks to a "blockchain".

Looking at the previous chapter, there are still some unanswered questions:

- Do AO nodes run all three of these "units"?
- How do Scheduler Units order trnasactions? 
- How do you know a Compute Unit will return you a correct result?
- Where is consensus?!?!?!?!?!?

In this chapter, based on the explanation of MUs, SUs, and CUs as well as other 
AO primitives, we will take a look at answering some of these questions and
looking at the security and consensus model of AO in more detail. 

Let's first take a look at consensus at the state level and build up from there.

## The state layer

As mentioned in the previous chapter, SUs order and store messages on Arweave,
and CUs perform computation based on this message log on Arweave.

This means at the state layer, consensus is solved. Once a set of messages are
on Arweave they are immutable and tamper-proof: in other words, anyone can read
from this log of messages stored on Arweave and re-construct the state of an AO
process.

AO essentially inherits the security of Arweave for the storing and reading of
message data. 

Arweave is the source of truth for settled transactions, so where some kind of
consensus is needed is instead *before* this, when messages are being propogated
through the network to be scheduled in a specific order.


This leaves two parts about consensus to be answered:
1. How do you ensure that Scheduler Units order transactions in a fair, and
   tamper-proof way?
2. How do you ensure that Compute Units return truthful results to a user?

## Consensus and trust from SUs

As mentioned in the previous chapter, Scheduler Units (SUs) are responsible for
deciding the order of messages, and settling them on Arweave. 

This means that *this* is the part of AO which requires consensus; in other
words determining the order to store messages related to a process.

## Ensuring computational correctness from CUs

Along with consensus on SUs, Compute Units (CUs) don't have a strict consensus
mechanism, but use economic incentives and staking in order to return correct
computational results for users.

CUs
