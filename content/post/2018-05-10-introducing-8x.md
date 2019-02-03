---
title: "Introducing the 8x Protocol"
date: 2018-05-10
tags: ["ethereum", "smart contracts", "8x"]
draft: false
---

Crypto currency’s first use case is payments. Blockchain technology enables
fast, secure and borderless payments to occur. However there’s still a long way
until payments as a use case is fully realised.

For example, the volatile nature of the crypto market makes it an unsuitable
exchange of value for retailers and consumers paying for real world products and
services. One Ether was worth almost $1500 in January only to be worth a third
of that four months later. To expect a business to deal with such volatility is
unreasonable at best.

In addition to facilitating stable exchanges of value, there isn’t any way to
facilitate a stable recurring transfer of value between two parties. Put more
plainly, there isn’t any way of enabling stable, recurring payments on the
blockchain.

*****

### Problem

> Recurring payment crypto arrangements do not exist

Recurring payments as a use case is a pretty major one — so why hasn’t this been
problem solved?<br>  There’s three main issues which make it more complicated
that simply deploying a smart contract:

1. Programming stability into smart contract is hard. Relying on a 3rd party
service to provide accurate exchange rates puts too much trust in a single
party. In addition, once the exchange has happened the business still needs to
deal with the volatility of crypto currency markets.

2. Since users have to sign transactions with their private keys, you can’t
“pull” Ether from them directly. The most obvious option is to store funds
inside an escrow contract which has custody of your funds. However this opens up
the system to attacks from black-hat hackers who like to target high net-worth
contracts eg. The DAO.

3. Making sure the system is technically viable has it’s own set of challenges.
In order for a smart contract to have scheduled execution (call this contract
every 30 days) isn’t possible with existing infrastructure. While you could use
an external server to trigger the smart contract, any downtime of that server
could lead to loss in funds for businesses due to missed scheduled executions.

*****

### Solution

8x is an Ethereum based protocol that aims to abstract these complexities away
and make it simple for businesses to accept cryptocurrency as a means of
payment. It aims to solve this through the following mechanisms: <br>  <br>  1.
Rather than programming stability, the 8x facilitates stable coins such as
MakerDao as the underlying mechanism for transfer of value. To learn more about
how MakerDao keeps a 1:1 peg to the USD read:

[https://medium.com/cryptolinks/maker-for-dummies-a-plain-english-explanation-of-the-dai-stablecoin-e4481d79b90](https://medium.com/cryptolinks/maker-for-dummies-a-plain-english-explanation-of-the-dai-stablecoin-e4481d79b90).

2. Stable coins such as MakerDao are ERC20 compliant. What this essentially
means is that you can “approve” another address (such as a smart contract) to
spend tokens on your behalf. The 8x protocol utilises this by asking users for
permission to spend Dai so no funds are held by the smart contract.

3. When a user subscribes to a plan, the transaction is emitted to a network of
“processors” who hold 8x tokens. These processors have the ability to claim the
right to execute the payment when it’s due in the by staking 8x tokens
proportionally to the value of the subscription. As a reward for executing the
transaction at the correct time, processors take a 1% cut of the subscription
(paid in the stable coin not 8x tokens) and receive their staked 8x tokens back.
Failing to execute the transaction will result in their stake being slashed.

*****

### Why?

Having new technologies such as blockchain are great, although they don’t mean
much unless they can offer a significant improvement over the existing system.
The 8x protocol offers the following benefits for business and users:

— Businesses: existing credit card processors such as Stripe and Paypal charge
2.9% + 30c fee to retailers for every payment made. 8x will allow this fee to be
reduced to 1% + gas fees.<br> — Users: all your subscriptions can be viewed and
managed in a single interface. Rather than stumbling through a businesses
website to cancel a subscription, you can do it through a unified interface.

*****

### Vision

Money is just the vehicle for the exchange of value between two entities. 8x
aims to be the underlying mechanism for the exchange of recurring value to
occur. Part of this involves creating a global fiat settling layer that allows
businesses to accept crypto currencies and receive cash payments into their bank
account without any knowledge about crypto whatsoever. Furthermore, the entire
protocol will eventually be run and governed by processors/token holders who
will ensure the protocol thrives and adapts.

*****

### Closing

If you believe in the project and it’s potential impact I’d love to hear from
you to learn how you could get involved. This post gives a brief overview of the
protocol, however if you’d like a more detailed view on concerns such as gas
costs, claim conflicts and more you can read the white paper at:
github.com/8x-protocol/whitepaper.

* [Blockchain](https://medium.com/tag/blockchain?source=post)
* [Cryptocurrency](https://medium.com/tag/cryptocurrency?source=post)
* [Protocol Tokens](https://medium.com/tag/protocol-tokens?source=post)
* [Ethereum](https://medium.com/tag/ethereum?source=post)

### [Kerman Kohli](https://medium.com/@kermankohli)

Founder 8x Protocol

### [8x Protocol](https://medium.com/8xprotocol?source=footer_card)

Pay your subscriptions with crypto.

Another useful feature would be the ability to set up recurring payments for
services or products that don’t have a subscription. Like refilling my bus pass
every month.
