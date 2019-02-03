---
title: "How does Ethereum work?"
date: 2018-04-26
tags: ["ethereum", "smart contracts"]
draft: false
---

Ever since its launch in 2015, there’s been a lot of talk around Ethereum from
it’s $150M “hack” to the various token economies it has spawned.

Before we get started there’s a few things you need to know about

**Externally Owned Accounts:**<br>  — Contain Ether<br>  — Ability to make
transaction on the network<br>  — Requires private key to operate<br>  — Does
not rely on any code

**Smart Contracts:**<br>  — Contain Ether<br>  — Are operated through code<br> 
— Store state of a program (can run programmable decentralised applications)

As mentioned in my last post about gas
[https://medium.com/@kermankohli/smart-contract-security-pt-iii-gas-limits-4c48c7d0eba0](https://medium.com/@kermankohli/smart-contract-security-pt-iii-gas-limits-4c48c7d0eba0),
every transaction made on the network requires gas to be paid. A transaction
could be you sending money to your friend, or it could be interacting with a
smart contract.

### State

In Bitcoin, your “balance” is simply the remaining balance from a series of
transactions. You don’t actually own Bitcoin in your wallet, just authorisation
to make another transaction. It also means to get your balance you need to
retrace a series of transactions.

In contrast, every transaction made on the Ethereum network updates its world
state meaning you can query any information you have by having the latest
version of the public ledger. It can verify the world state is correct through
its state, storage, transaction and receipts trees (referred to a as tries
formally).

To make this a bit more relatable, an ICO is simply a smart-contract that issues
tokens to users who send it Ether.

**So how does the process work when you buy a token in an ICO?**<br> - You sign
a transaction with your private key to send Ether to the address of the smart
contract hosting the token.<br> - Based on the computational work required for
the miners to interact with the smart contract processing your transaction, a
gas fee is charged. The less you pay in gas fees the less incentive miners have
to process your request, hence the more gas you pay the quicker your transaction
will be added to the next block.<br> - Assuming the gas to work ratio is
worthwhile enough at the time, your transaction will be added into the next
“block” mined. <br> - This mined block containing your transaction is
broadcasted to the network and the global state is updated.

What this means is that any transaction made to a smart contract is executed by
every miner on the network, essentially Ethereum is a global computer which
can’t be stopped! I’ll be writing another article that talks about the potential
problems with the law and smart contract execution later.

*****

Interacting with a smart contract, isn’t something that everyday want to do, or
should do. That’s why extensions such as Metamask exist which create easy to use
interfaces with interacting with the blockchain and it’s various ecosystem
components.
