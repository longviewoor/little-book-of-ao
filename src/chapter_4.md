# Consensus and Global State

What you might have realized so far in our discussion of AO's architecutre is
that there has been no mention of "blocks", or adding blocks to a "blockchain".

This is where AO *is* different to many blockchains out there. 

As mentioned in the previous chapter in the section on Compute Units (CUs), each
and every process and message is stored in chronological order on Arweave.

This means AO nodes themselves do not store state - they are instead focused largely on execution and message passing. 

There is no need for consensus once the state has been settled on Arweave, as
Arweave acts as the state layer. 

If a set of transactions related to a process are stored immutably, anyone can
read this from Arweave, and re-construct this set of ordered messages to get the
state themselves.

Arweave is the source of truth for settled transactions, so where some kind of
consensus is needed is instead *before* this, when messages are being propogated
through the network to be scheduled in a specific order.

## Consensus 

As mentioned in the previous chapter, Scheduler Units (SUs) are responsible for
deciding the order of messages, and settling them on Arweave. 

This means that *this* is the part of AO which requires consensus; in other
words determining the order to store messages related to a process.

## Computational Correctness

Along with consensus on SUs, Compute Units (CUs) don't have a strict consensus
mechanism, but use economic incentives and staking in order to return correct
computational results for users.

CUs
