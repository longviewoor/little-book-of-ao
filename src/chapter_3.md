# Transaction Lifecycle 

On AO, users have a wallet with which they create and sign transactions, also
known as **messages** on AO. 

Let's take a look at a high-level overview of what happens when a message is
sent on AO, and how a user gets a response from the network. 

## Message validation

When a user interacts with a dApp on AO, for example a decentralized exchange
process, a message is created and sent to an initial node.

This initial node receives the new message, checks to see if the transaction is
valid (for example it has a valid signature, has the correct structure, etc.).

If the message is valid, it forwards this message onwards to be scheduled.

## Message scheduling and storage

Once a message is deemed as valid, this means it can be scheduled for settlement
and storage on Arweave.

A scheduler handles all of incoming messages associated with certain processes,
orders them, and then stores these messages on Arweave. 

This is a crucial part of the process, as it sets in stone the transaction ordering.

Each message is stored on Arweave in an immutable, timestamped order - just like
with other blockchains. 

## Computation

Once a user's message is stored on Arweave, the new state of a process can be
computed.

Think of it like this:

- An AO node sends off a message to be stored on Arweave
- Schedulers handle the message settlement, and once done, let the AO node know
- The AO node can now *read* all the transactions on Arweave, and re-construct
  the state
- A number of AO nodes can compute this state for further verification 

And this is exactly what happens with AO. An AO node reads all of the state
associated with a process from Arweave, computes it, and returns the result to
the user.

This is ultimately how the message lifecycle works on AO.

## But, where consensus?

This approach to computation is radically different to other solutions, which
also means that consensus must also be approached differently.

Let's take a look at consensus in a little bit more detail.
