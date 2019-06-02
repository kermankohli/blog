
---
title: "The State of Crypto Interoperability."
date: 2019-04-18
tags: ["ethereum", "crypto", "interoperability", "cosmos", "polkadot"]
draft: false
---

### Introduction

There’s been a lot of talk about blockchain interoperability recently with the
launch of Cosmos and the potential threat to the Ethereum ecosystem. This piece
is going to be a** deep dive** on the technicalities of **Cosmos and Polkadot**,
but will also give you the prerequisite knowledge you need to understand these
protocols at a technical level (with pictures to help understand).

Firstly, it’s important to know **why interoperability** matters. In the
existing internet, we can access and modify numerous data sets through APIs
(application specific interfaces). However with blockchains, data is siloed by
the chain that it exists on. So what does it mean to have interoperability?

1.  **Trustlessly transfer** assets between different chains
1.  **Cross-chain smart contracts** that can interact with each other
1.  **Specialised chains** that can be used by other blockchains

Before we get into the details of any particular interoperability approach, I’d
like to spend some time outlining some of the **basics of distributed systems**
in order to help us understand concepts later on. Keep in mind that blockchains
are simply a **set of machines** all over the world coming to an agreement about
what a collection of data should look like.

### Distributed Systems

Distributed systems are, as the name implies, a group of computers **working
together** to accomplish a very **specific goal**. An example of this goal might
be to serve the same content around the world to lots of people (like keeping
your Twitter newsfeed up to date). In trying to achieve this goal they have to
overcome the following problems:

1.  **Timing**. Each computer/system will execute the same task at it’s own pace and
time.
1.  **Ordering**. Trying to solve what happened and when with time is still very
hard since clocks start “drifting” after a period of time. This makes order a
complicated challenge since each system has its own account of what happened and
when.
1.  **Failure**. Coordination between systems can fail due to a system crashing, not
receiving/sending messages to other systems correctly or choosing to act
maliciously (**Byzantine**)

Like humans, the way to solve most problems is through good communication. With
computers though, this is a bit more complicated since they can communicate
**asynchronously** or **synchronously**.

What does that mean?

* **Synchronous** = each system has a certain amount of time allocated to them to
communicate and they take turns. Think of it in-real conversations for humans.
* **Asynchronous** = each system can communicate whenever they want and there’s no
assumptions about when they’ll speak. Think of it as Slack for humans.

All said and done, at the end of the day a blockchain should have **safety**
(agreement on the same output) and **liveliness** (chain keeps growing and
functioning). If your chain has safety but not liveliness it’ll **stop producing
blocks**. If it has liveliness but no safety it’ll **produce many forks** and
you won’t know which one is the correct blockchain unless you have a rule (eg
longest chain in Bitcoin)!

### Introducing Practical Byzantine Fault Tolerance (PBFT)

Practical Byzantine Fault Tolerance is an implementation developed by **Barbara
Liskov** and **Miguel Castro** and introduced in 1999. Proof of Stake chains
like Cosmos and Polkadot have elements in their design inspired from PBFT so
it’s worth outlining what it is and how it works.

1.  A party will listen to numerous transactions until it can form a block of these
transactions. We’ll refer to this party as a **proposer**, since they **propose
**a block.
1.  Once a block has been proposed, everyone participates in a **pre-vote** to
confirm that they heard the same block. It’s important to note that a block
could be incorrect/malicious but still be valid in the pre-vote stage since
everyone’s simply trying to come to consensus that they received the **same**
data/block.
1.  Once more than ⅔ of the participants agree that they received the same block,
they move to the **pre-commit **step. A pre-commit vote is then cast to
determine whether this is a **valid** block and nothing malicious is going on.
1.  If more than ⅔ of the participants vote that the block is indeed valid and
correct then we can successfully **commit** this block to the blockchain.
1.  The height of the blockchain is increased and steps 1–5 are repeated.

From what we’ve learned above, we can see that the following steps ensures that
the **order** of blocks is known (by the height of the blockchain increasing
once a commit happens), each computer can take it’s time to come to its own
conclusion then communicate what result it came to (**timing**) and can handle
**failure** (malicious node proposing a block or a node not being able to vote).

### Hello Cosmos!

Enter Cosmos, founded in 2016 by Jae Kwon and Ethan Buchman and raised over
**$17M**+ in their ICO for ATOMs. The Cosmos **Hub** is it’s **own blockchain**
that connects to other zones (blockchains) and therefore allows communication
between different zones. Any proof-of-work blockchain such as Bitcoin, Ethereum,
ZCash or an application specific blockchain would have to be connected to a
bridge-zone via the Inter Blockchain Communication framework.

Getting into the architectural details, Cosmos Hub uses **Tendermint** as it’s
consensus algorithm (inspired by PBFT) created by Jae Kwon in 2014. What this
means is that each voting stage (pre-vote & pre-commit) has a fixed amount of
time for everyone to vote before it moves on to the next stage. After a block
has been finalised, there’s no going back. This means you can have instant
mobile & internet-of-things payments since as soon as the transaction is in a
block it’s finalised. Since **no confirmations** are required this is called
having “fast finality”.

ATOMs held by users can be used to **become validators** in the system or to
**delegate** ATOMs to a validator instead. The Cosmos blockchain will have **100
validators** to begin with and plan to increase the limit via a governance
parameter in the future. Only those with reasonable power in the network will be
able to participate in the security of the network.

To make all of this less theoretical, I’ll outline a set of steps to possibly to
convert **ETH to BTC**. — everyone’s favourite example.

1.  A **trusted intermediary zone** will be created for Ethereum and there will be
set of validators who will be responsible for relaying messages from the
Ethereum bridge-zone to the Cosmos Hub.
1.  Since both Ethereum and Bitcoin are probabilistic (there is a chance the current
chain isn’t the correct one), the validators need to **wait** for a certain
number of **confirmations** to ensure the transaction actually went through.
1.  Once the validators are certain the transaction is final they’ll initiate a
transaction from their zone to the Cosmos Hub that they did indeed receive the
Ether. The hub will then **create** a form of **Wrapped Cosmos Ether** that
it’ll hold. Every other Cosmos zone will now be aware there’s new Wrapped Cosmos
Ether in the system.
1.  Assuming an exchange rate was determined beforehand, the Wrapped Cosmos Ether
will be **exchanged** for Wrapped Cosmos Bitcoin. This Wrapped Cosmos Bitcoin is
then **sent** to the trusted intermediary Bitcoin zone and sent to the specified
address on the actual Bitcoin chain.

There’s a few assumptions/things to be aware of with this model:

* The Cosmos Hub needs to ensure the balances of the Wrapped Cosmos assets are
correctly incremented and decremented. While this is a potential downside, the
Cosmos team has designed the system in a way that anyone can create their own
hub. Essentially Cosmos will be a network of Hubs and Zones run by different
groups.
* Each Zone has to be trusted that they’re relaying the correct messages about
assets being sent/received. Senders also need to trust the validators set will
correctly relay their messages and not steal their assets.

### Entering Polkadot

Polkadot is founded by Gavin Wood, a cofounder and former CTO of Ethereum and
president of the Web3 Foundation. Polkadot raised over 145M+ late 2017 selling
the native currency DOT during a crowdsale. If Cosmos resembles an open network
of hubs and zones, Polkadot is a single “relay chain” which offers numerous
benefits to chains, called “parachains” (short for *parallelizable chains)*,
that join it.

A couple key aspects Polkadot aims to innovate are:

* Each parachain gain **pooled security** from the validator set of the relay
chain. Once a chain has connected to the Polkadot network by becoming a
parachain it is secured with the same level of security as the whole Polkadot
network. In Cosmos, each new chain needs its own validator set and has to
bootstrap its own security.
* Parachains can interact with other parachains using **trust-fee interchain
communication. **Users who want to communicate across chains do not need to
trust every chain they transmit messages to, but just the singular security of
the whole Polkadot network. Again, this is different from how Cosmos works where
a user would need to trust the source chain, the routing chains, and the
destination chain with each of their separate validator sets.

Polkadot’s consensus mechanism consists of two components: **GRANDPA **and
**BABE**. GRANDPA is a finality gadget which draws on some ideas behind the
GHOST fork choice rule (like Ethereum’s Casper) and BABE is a block production
mechanism similar to Cardano’s Ouroboros. The introduction of a finality gadget
allows for portions of the chain to be “finalized” and provably never be
reverted. Separating the finality gadget from the block production allows for
the slower finality gadget to work in a different process from the generation of
new blocks in the chain. This means that the actual production of blocks can
scale unlike in the PBFT-bound Cosmos Tendermint algorithm.

In the Polkadot ecosystem, you have the following parties:

* **Collators** — Produce the blocks for parachains and pass the information to
the validators to verify.
* **Nominator **— Allocates their capital to validators to participate in the
staking mechanism.
* **Validator **— Require a high bond requirement because they are responsible for
actually sealing the new blocks of the relay chain. Their crucial roles include:
* *Authoring new blocks.*
* *Finalizing the relay chain through participation in GRANDPA.*
* *Validating parachain blocks by ensuring the transactions which occurred are
correct and that the cross-chain messages have been processed.*
* **Fishermen **— Bounty hunters who “go fishing” for malicious actors by watching
the other nodes of the network.

A good way to think about Polkadot is as an interconnected system that will
connect to other chains it will want to communicate with through bridges. All
parachains and the relay chain operate as **one, unified system. **A parachain
can incorporate custom logic and will be responsible for handling its own state
transitions while receiving and posting messages to other chains. Parachains
will be able to **communicate with other parachains **by listening to each
other, unlike Cosmos where everything must be routed through the Hub.

Polkadot’s architecture is elegant for the core design assumptions it had made.
This starts off with the fact that parachain **passively read information** from
bridge-contracts, rather than relying on bridge-contracts sending messages to
other parachains. Each parachain is treated **no different** to any other
parachain. This means Polkadot’s interchain communication framework is truly
trustless, since parachains are acting in the interest of the relay chain rather
than any specific parachain they’re validating. Furthermore, validators are
**re-assigned **to another parachain at intervals and at random.

Let’s take an example that might be more relatable, how would it work if you
wanted to convert currencies from one parachain to another? Let’s take the
popular example of converting ETH to BTC.

**Collators** for the Ethereum parachain would pass block headers to validators
in their parachain. The **validators** would then sign and publish the relevant
transactions in the Ethereum bridge smart contract in a format that can be
recognised and communicated with the **parachain** zone. Any ETH sent would be
held by a Polkadot validator set, which would also provide DOTs as collateral
for invalid transactions. The Ethereum parachain would in turn communicate with
the Bitcoin parachain, which would release BTC to the specified address through
the validator set governing that particular parachain. Design decisions are
still being finalised, but the idea around their cross chain communication is
that it’ll be trustless.

One thing to be aware of is that Polkadot’s parachain mechanism will allocate
parachain slots via permissionless on-chain auctions. These auctions would
involve locking up DOTs for some amount of time to keep the parachain connected
to the Polkadot network. Governance will be able to step in and fix the
situation in the case of urgent situations where the parachains contains a
critical bug or serves some malicious purpose. Polkadot will be governed by an
on-chain governance mechanism as it believes it’s the best way to govern
crypto-networks.

> As Gavin Wood stated for this article, “I believe any blockchains that do not
> introduce on-chain governance, including providing a viable mechanism to issue
upgrades, will ultimately poison themselves through toxic populism. I do not
believe “off-chain processes”, “on-chain signalling” and “rough consensus”
provide a sufficient means to allow the real stakeholders in chain’s ecosystem
to effectively govern and drive a chain to long term success. I also believe
that it’s essentially impossible to retrofit governance.”

### Timelines

A lot of the core problems for interoperability seem to be solved at a high
level, however the execution is still far behind. Cosmos launched in March 2019,
but has only got the Cosmos Hub up and running. Their next steps are to finalise
how the **Inter-Blockchain Communication** framework will work. Polkadot is set
to launch **end of 2019** with just the relay chain being live.

Overall, I’m extremely excited for both Cosmos and Polkadot to launch. What’ll
be interesting to see is the developer adoption and the political struggles of
each chain and how they play out. Application specific chains are a pipe dream
at this point in time since not only is the basic infrastructure far from being
completed, but developers will need to think about the **resources and people**
they’ll need behind them to be connected and have sufficient security.

Will it even be a relevant trade-off? It’s hard to say. Maybe **Ethereum’s
off-chain governance** is the very thing that allows it to thrive despite it’s
slower roadmap execution since it allows true permissionless innovation with the
guarantees of a highly secured chain.

The flip side to this argument is that all crypto networks will bootstrap their
security on another chain, such as Ethereum, and then graduate to their own
chain once they can guarantee the security of it through its existing community.
A good example would be **MakerDAO**, they’d have enough resources to create
their own chain and get enough political backing to be part of Polkadot’s
para-chain. If for some reason it can’t get enough backing to be a part of the
para-chain, it could establish a bridge zone on **Cosmos** and bootstrap their
own security. Polkadot plans to provide **bridge-slots** for chains that are
unable to provide pooled security but still give message passing down the line.

I think these are the kinds of nuanced questions that we as a community need to
be asking rather than looking at chains as a zero-sum game. I’m personally
excited for where all this leads us to and am receptive to your feedback on this
piece. Reach out to me on Twitter **@kermankohli**.

*Special thanks to Gavin Wood (Web3 Foundation), Logan Saether (Web3
Foundation), Billy Rennekamp (Cosmos), Chjango Unchained (Cosmos) for their
contributions with ensuring the technical accuracy of the article.*