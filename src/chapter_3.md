# Communication between nodes 

Similarly to most blockchains, users create and sign a transaction, and send it
to a single node which propagates the transaction throughout the network.

AO nodes run three distinct pieces of software which handle this process, and
start to form some kind of consensus.

## The Messenger Unit (MU)

The first part of a message's lifecycle is sending it to an initial AO node to
be propagated throughout the AO network. 

When a new message enters the AO network, the Messenger Unit (MU) of the AO node
checks to see if a transaction is valid (in other words is signed, and has the
correct transaction structure).

If valid, the message is broadcasted to other AO nodes, and in turn, these are forwarded onto
the Scheduler Units (SUs).

## The Scheduler Unit (SU)

Processes on AO are assigned a Scheduler Unit (SU), which handles the sequencing
and ordering of messages related to that process. 

The SU will order any messages related to a given set of processes, and store
them as Arweave transactions. 

This sets in stone the transaction ordering, as each message is stored as a
signed transaction, on Arweave, in an immutable, timestamped order.

## The Compute Unit (CU)

Once a message has been sent to Arweave to be settled, it is relayed back to a
Compute Unit (CU) running on an AO Node.

The CU essentially takes the process, reads all of the messages associated with
that process (stored on Arweave) in order, and then uses that to determine the
state to return to the user. 

This means that nodes on AO don't technically store any kind of state - they
just read it from Arweave on demand, which *is* storing it. This is referred to
as **holographic state** on AO. 

