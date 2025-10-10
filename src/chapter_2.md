# AO Nodes, Processes, and Messages

## AO Nodes

An AO node is a computer running [HyperBEAM](https://hyperbeam.arweave.net), AO's node client software. 

These nodes operate similarly to other blockchain nodes: they communicate with
each other over a network, handle transactions, compute smart contract state, and more.  

For now, let's focus on the primary purpose of these nodes: **performing
computation**.

Users of blockchains and decentralized networks want to be able to do things: transfer tokens from one account to another, swap tokens on decentralized exchanges, and interact with different types of smart contracts.

AO nodes facilitate these actions through two primary mechanisms: **processes** and **messages**.

## Processes

On AO, smart contracts are colloquially referred to as **processes**. Processes on AO are written in the [Lua](https://www.lua.org/) programming language. 
AO processes contain **handlers** which, as you might expect, "handle" different types of
transactions. 

These handlers are written by developers, and contain the logic to
deal with different types of smart contract actions.

For example, a decentralized exchange built on AO might have a process with the handlers "swap", "deposit", and "withdraw".

If a user sends a transaction of type "swap", the process runs the relevant code
to handle a swap. If it is deposit, it will run the code in the process for deposit the user's tokens into a pool. And so on.


## Messages

Transactions that users send to processes are referred to as **messages** on AO. Processes can also create and send messages to one another, much like how smart contracts can call other smart contracts.

Messages function identically to transactions, and in reality are signed
transactions which get settled onchain (which we'll look more into later).
Wehere you might think of blockchains as a chain of blocks, processes in AO have
their own "chain of messages" associated with them. 
