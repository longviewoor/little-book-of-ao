# Communication between nodes 

Similarly to most blockchains, users create and sign a transaction, and send it
to a single node which propagates the transaction throughout the network.

AO nodes run three distinct pieces of software which handle this process. One
part in particular, the Scheduler Units (SUs), are important for consensus.

In this chapter, we'll look at the different "units" which make up different
types of AO nodes, and slowly build up the connection between them.

## The Messenger Unit (MU)

The Messenger Unit (MU) is essentially the entry point and exit point of every
message sent by a user on AO. When users create a message to interact with a process, 
it is sent to the MU of an initial AO node to be propagated throughout the network. 

When an AO node receives a new message, the MU checks to see if a transaction is valid
(for example it has a valid signature, and has the correct transaction structure, etc.).

If valid, the message is broadcasted to other AO nodes. This part is much like
blockchains you might be familiar with - you post a transaction to the network
which is received by an initial node, which then shares it to other nodes.

On AO, valid messages are propogated throughout the network and forwarded onto
**Scheduler Units** (SUs). 


## The Scheduler Unit (SU)


SUs are special kinds of nodes which have one major job in the AO network:
sequencing and ordering messages for processes.

Let's take, for example, a standard process for a decentralized exchange. 
If 10 different users send messages to make swaps, these need to be put in some
kind of order for the process to handle. This is the job of Scheduler Units. 

When a process is deployed on AO, it is assigned a Scheduler Unit (SU). The SU
will order any messages related to a given set of processes for processing. 

This is a very important part of a message's lifecycle, as it is also the part 
where data gets stored **onchain**. 

As mentioned in the last chapter, messages are signed Arweavetransactions, in the
format of [ANS-104 DataItems](https://cookbook.arweave.net/tooling/specs/ans/ANS-104.html). 

What this means in practice is that AO messages are transactions which an SU puts in order,
then stores onchain, on Arweave. 

This is a crucial part of the process as it sets in stone the transaction ordering.
Each message stored on Arweave is in an immutable, timestamped order.

## The Compute Unit (CU)

Once a SU has sent a message to Arweave to be settled, it is relayed back to a
Compute Unit (CU).

The CU is an AO node which handles the actual computation of state to relay data 
back to the user. Here's where AO gets very interesting.

For the CU to work out the current state of a process, all it has to do is read
in the process (stored on Arweave), along with all of its associated messages in 
order. By doing this, it can determine the current state to return to the user.

Note the interesting property here: state is simply implied on Arweave, and
computed on demand. Users could even spin up their own CU to verify the state
themselves.

This means that nodes on AO don't technically store any kind of long-term state - they
just read it from Arweave on demand, which *is* storing it. 

This concept is referred to as **holographic state** on AO.

