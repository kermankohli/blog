
---
title: "What’s MakerDAO and what’s going on with it? Explained with pictures."
date: 2019-03-13
tags: ["ethereum", "makerdao", "technology"]
draft: false
---

# What’s MakerDAO and what’s going on with it? Explained with pictures.

![](https://cdn-images-1.medium.com/max/800/1*o9Q_RfcTwYPJXxcdlaw-rg.jpeg)

### What is MakerDAO?

MakerDAO is a [protocol](https://hackernoon.com/tagged/protocol) behind the
stable coin DAI — a
[cryptocurrency](https://hackernoon.com/tagged/cryptocurrency) that maintains a
1:1 peg to the USD. Think of 1 DAI as $1. What makes it unique is each DAI is
backed by Ether instead of a 3rd party claiming to have the required collateral.
Since Ether is volatile this poses some interesting challenges to maintain the
peg.

![](https://cdn-images-1.medium.com/max/800/1*2CY0sTQG7l7DZnYa0FqtHQ.jpeg)

The project was started in 2015 and did not conduct an ICO, instead choosing to
privately sell MKR tokens to fund development over time. Maker’s DAI stable coin
launched at the start of 2018 and has experienced significant traction since
then.

#### Why do we need DAI?

Dealing with crypto’s volatility is a problem. As many in the blockchain space
know, DAI is not the first stable coin in the space. Predecessors include
Tether, TrueUSD and a few others. However the risk of all of these projects is
that the custodial party holding the real US dollars will refuse redemption of
the stable coin for any regulatory reasons. This goes against the ethos of
crypto being permissionless. Furthermore, we have to trust that the custodial
solution actually has the correct amount of US dollars and not creating
artificial inflation.

#### Who’s using it?

DAI is arguably the most successful project built on Ethereum at this point in
time. It currently holds 2% of all Ether inside its smart contracts and has
issued over $77 MM in DAI (debt) in its system. In addition, Maker continues to
see perpetual 20% month-on-month growth in terms of the DAI issued with 71% of
users spending their DAI as soon as they acquire it. This signals a shift of
usage rather than speculation.

![](https://cdn-images-1.medium.com/max/800/0*j1OL0yFSoD0qo5lI)
<span class="figcaption_hack">Source:
[https://medium.com/makerdao/dai-in-numbers-2710d8a5633a](https://medium.com/makerdao/dai-in-numbers-2710d8a5633a)</span>

*****

### How does it work?

The basics of the system, work like this:

* You deposit/send Ether to Maker’s smart contract, creating a Collateralised Debt
Position (CDP).

![](https://cdn-images-1.medium.com/max/800/1*Xhx15qip8d-eImRUBfMEEA.jpeg)

* Say you deposited 1 ETH (worth $100), this will allow you to take up to 40 DAI
(assuming a 150% collateralisation rate $100/1.50) against your $100. However,
if the price of Ether drops below $100 your CDP will be forcefully closed. To
stop this from happening you need to put in more Ether or take out less DAI in
the first place. **This is to ensure there’s always enough capital locked
against the amount of money being taken out.**

![](https://cdn-images-1.medium.com/max/800/1*JCn3yaLh1bXURKXUKqPGNg.jpeg)

* If you want your Ether back, you need to pay back the amount you took out with
the addition of a minor fee.

![](https://cdn-images-1.medium.com/max/800/1*t8i6-iDOiu80_LxOZ3-Gmg.jpeg)

It can be a bit overwhelming.

Here’s a **few simple examples **of how the lifecycle of a CDP might play out
assuming the price of Ethereum is $150 and you deposit 1 ETH at this price:

1.  You decide to take out **50 DAI** which means your CDP is collateralised
**300%**. As long as the price of Ethereum doesn’t drop below **$75** (50 *
150%) your position will be safe. After one year, you decide to pay back the
**50 DAI** and retrieve your Ether locked up. Upon closing the position or other
interactions with your CDP, you’ll pay the annual stability fee (set at 3**.5%**
as of March 2019).
1.  You decide to take out **100 DAI** which means your CDP is collateralise at just
**150%**. The price of Ethereum drops to **$100** which means your CDP is
under-collateralised by **$50** ($100*1.5 = $150 < $100). A 3rd party will
realise that you don’t have enough collateral and liquidate your CDP on your
behalf. This results in your position being liquidated by 3rd parties with a
penalty. These 3rd parties have various ways to profit from your position being
liquidated.
1.  You decide to take out **75 DAI** which means your CDP is collateralised at
**200%**. The price of Ethereum rises to **$300** due to the bull market
starting. Your CDP is now collateralised at **400%**. Since you’re an ETH bull
and you think the price won’t go down, you decide to draw an extra **100 extra
DAI **putting your CDP ratio at **175%**.

*****

### Who Controls the System?

Inside the MakerDAO ecosystem, their native MKR token allows token holders to
influence certain aspects of the protocol such as:

* What should the be the annual borrowing fee be (**stability fee**)?
* How much collateral should be backing each CDP (**collateralisation ratio**)?
* Shutting down the protocol in the case of a flash crash of the price of Ether or
any other unforeseen situation (**emergency shutdown**)?

One important piece of information I haven’t mentioned so far is the fact that
when the stability fee is paid, a **dollar equivalent amount of MKR** is
purchased off the market to pay the stability fee. This means that MKR is
actually a **deflationary currency**.

At its core, MakerDAO is like a** credit facility** that issues loans with a
certain interest rate. If the interest rate (stability fee) is low, people are
encouraged to borrow more (lock up more ETH). If the interest rate is high, the
cost of capital is high making it less attractive to borrow (close out CDPs).
Recently, DAI has been consistently been** trading on exchanges below $1**. A
big reason for this is because there is significant pressure from DAI holders to
sell. DAI can only be generated via the opening of CDPs. To bring the peg back
to its correct target price, MKR holders voted to **increase** the stability fee
**from 1% to 3.5%** in hopes that it reduces the incentive to open CDP (and
close existing CDPs) to** increase the buy pressure**. In the future the Maker
team plans to introduce the Dai Savings Rate, which will allow DAI holders to
lock up their DAI and earn interest. The interest paid to holders is financed
from the stability fee that currently goes to purchase and burn MKR.

Now in the case that the MakerDAO system contains less collateral than it’s
supposed to (flash crash of Ether), additional MKR is issued and sold on the
open market to pay back ETH and DAI holders. It is for this reason that MKR
holders don’t want to set the collateralisation ratio too low as they’re the
buyers of last resort. However, they don’t want to set it too high as the cost
to borrow increases.

#### Positive ETH Feedback Loop

A type of behaviour that we can’t confirm but can speculate happens is CDP
holders doubling down on their positions (or going “long” on ETH).

Essentially it goes a little like this:

* **Open a CDP** with a 200% collateralisation ratio
* **Wait** for the price of Ethereum to appreciate
* **Draw more DAI** from your CDP (because you can without decreasing your
collateralisation ratio)
* **Purchase more ETH** with your newly minted DAI
* **Add** **ETH** **to** **your** **CDP** to over collateralise your CDP to
safeguard against any market down turns

While it sounds quite harmless, tomorrow if ETH appreciates to $500 from its
current $150 price, the current 250% collateralisation ratio (average) would
increase to 75900%. Based on current numbers it means 150M dai could be minted
which could cause significant buy pressure on Ether causing a positive feedback
loop. The current 100M debt ceiling limits this from happening but will most
likely be increase with the introduction of multi-collateral DAI.

*****

### Multi-Collateral DAI

So far the MakerDAO experiment seems to be a success amongst the community and
is growing every month. However a big limitation is you can only use Ether to
collateralise your CDPs. With the introduction of multi-collateral DAI you could
use any ERC20 token to collateralise your CDP. You could actually use your
wrapped Bitcoin to collateralise your CDP!

While it all sounds good there’s two implications which Maker fans should be
aware of:

1.  Using custodial assets such as wrapped Bitcoin (backed by BitGo) could result in
undercollateralised CDPs if issuers are forced to freeze assets. An example of
this is authorities telling BitGo they’d like to blacklist wrapped Bitcoin from
MakerDAO’s addresses. This means that the value of the Bitcoin backing the CDP
is worthless.
1.  Since Ethereum isn’t the only asset inside the collateral, it means that any
positive feedback loops from the ETH price can’t be realised as there’s less ETH
to actually contribute. I don’t see this necessarily being a bad thing but it’s
worth being aware of.

*****

### Final Remarks

Thing such as the positive ETH feedback loop and Dai Saving Rate are going to be
really exciting to see come to life as we’ve never seen anything like it at
scale. Coupled with all the other open finance projects, this experiment is
going to be exciting to see play out!

I personally think Maker is the third most successful experiment after Bitcoin
and Ethereum. The team has stayed true to the values of crypto, engages with the
community and has shipped a meaningful contribution to the entire space.

They also throw amazing parties but that’s for another time.

#### References:

* [https://hackernoon.com/an-overview-of-makerdao-21e9f34aa1f3](https://hackernoon.com/an-overview-of-makerdao-21e9f34aa1f3)
* [https://medium.com/makerdao/dai-in-numbers-2710d8a5633a](https://medium.com/makerdao/dai-in-numbers-2710d8a5633a)
* [https://medium.com/pov-crypto/evaluating-mkr-def6d36092bd](https://medium.com/pov-crypto/evaluating-mkr-def6d36092bd)
* [https://medium.com/pov-crypto/could-makerdao-trigger-a-positive-feedback-loop-of-increasing-eth-price-fce80b27119](https://medium.com/pov-crypto/could-makerdao-trigger-a-positive-feedback-loop-of-increasing-eth-price-fce80b27119)
* [https://medium.com/makerdao/raise-the-stability-fee-to-3-5-f0d6731b1041](https://medium.com/makerdao/raise-the-stability-fee-to-3-5-f0d6731b1041)
* [https://medium.com/@visionhill_/a-makerdao-case-study-47a31d858be5](https://medium.com/@visionhill_/a-makerdao-case-study-47a31d858be5)
* [https://www.reddit.com/r/MakerDAO/comments/asb9n6/a_couple_questions_concerns_about_maker_and_mkr/](https://www.reddit.com/r/MakerDAO/comments/asb9n6/a_couple_questions_concerns_about_maker_and_mkr/)
* [https://medium.com/makerdao/dai-reward-rate-earn-a-reward-from-holding-dai-10a07f52f3cf](https://medium.com/makerdao/dai-reward-rate-earn-a-reward-from-holding-dai-10a07f52f3cf)
