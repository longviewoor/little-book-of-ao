# Scaling

As AO has no blocks or blockchain, this means it does not 
have a **global shared state**.

There is no global state for AO nodes to agree upon, as this state is
stored on and read from Arweave.

This radically changes how AO can scale - as interactions with different processes
do not have to wait in a queue to compute state, it allows for massively parallel
execution. 

Let's explore this with a more concrete example. 

## Sending messages at the same time

Let's assume that one user, Bob, wants to swap some tokens
on a decentralized exchange. 

He will send a message to the DEX process, usually through a dApp's interface,
leading to a transaction lifecycle like we've already explored.

Now let's say at the same time, Alice wants to buy an NFT (Atomic Asset) from
a marketplace, with a similiar transaction lifecycle. 

These two actions do not modify the same state - so what's to say that they
cannot happen simultaneously? 


based on what we've explored in the previous chapters, we can see that not 
**all** AO nodes must compute **all** actions. In fact, users can provision 
as little or as many nodes as desired to verify the result of an action. 

What this does mean though is that while Bob is sending his message to AO Node
1, Alice can, at the same time, send her message to AO Node 2. Both can get
their results back from these different nodes, without waiting for them to agree
agree upon consensus.

Processes are instead concerned with largely with their own state. 

## Horizontal scaling

With traditional blockchains, adding more nodes to the network doesn't 
tend to increase the speed or scalability of a blockchain. 

Every node must agree on every transaction and every state change, and update
their state accordingly. This is a scaling bottleneck that is solved by Layer 2 
solutions such as rollups. 

With AO, the more nodes on the network means the more nodes available for
computation, which means the more processes can execute in parallel.

This is what's known as **horizontal scaling**. 

## Accessing the same process

To go a step further, what if Bob and Alice *did* want to access the same
process?

In this case, the messages would get queued in the inbox of a process, and there
would be a similar aspect of waiting for a result. 

However, this can still be alleviated yet by sharding the process, or splitting
it into multiple processes, and routing user messages to the process with the
lowest amount of messages queued for processing. 

This is ideal for use cases that typically become infeasible in pracitce, such
as large scale onchain games or social media applications.

## Conclusion

This covers most of the building blocks and core concepts which underpin the AO
network. 

If you'd like to learn about the architectural concepts in more detail, or
explore other novel aspects of AO, please check out the references section.
