---
title: "Say Hello to Subscription Payments on Ethereum."
date: 2018-10-06
tags: ["ethereum", "8x"]
draft: false
---

# Say Hello to Subscription Payments on Ethereum.

## Printf(“Hello Subscription Payments”)

![](https://cdn-images-1.medium.com/max/1600/1*BgehT4R5Vd_lOonusgmhcw.jpeg)

For the past few months at 8x, achieving subscription payments on the blockchain
has been our core focus. Since it’s inception earlier this year, we’ve made
numerous changes to the underlying protocol design and thinking about how an
appropriate end-user experience might look.

Today I’m super proud to announce we’ve been able to make that happen (on the
Kovan test net). We’ve got three components for you to try out.

1.  **Manage** — a convenient way for businesses and users to manage their
subscriptions/plans.
1.  **8x.Pay** — payment gateway to allow consumers to easily subscribe to a
subscription plan.
1.  **8x.js **— javascript library to allow you to interact with the underlying 8x
smart contracts directly. We’ve also got some really nice **documentation** for
you to check out too at [docs.8xprotocol.com](https://docs.8xprotocol.com/)

Both Manage and 8x.Pay use the official 8x.js library!

*****

### Manage

The manage portal allows businesses to create a subscription plan and allows
consumers to view, manage and cancel their subscriptions.

Here’s how you can create a plan as a merchant.

![](https://cdn-images-1.medium.com/max/1600/1*IMAW7I1LXAVUYf47NfPZyA.png)
<span class="figcaption_hack">You have the ability to set your company’s name, a short description, the
interval, a price and an external unique identifier which you can use to query
all subscriptions with.</span>

Once you’ve created a plan you can now use the “Plan Hash” to allow your
consumers to subscribe to your subscription plan.

![](https://cdn-images-1.medium.com/max/1600/1*cbk6pa21qED_2a82u96EqQ.png)
<span class="figcaption_hack">Your newly created plan now on the manage portal.</span>

*****

### 8x.Pay

8x.pay is a payment gateway that allows your consumers to subscribe directly to
your subscription plan. You can try it out by pasting a valid plan hash and
clicking the “Pay” button

![](https://cdn-images-1.medium.com/max/1600/1*Ay-KF0c7k11UzBsWLBv6Tw.png)
<span class="figcaption_hack">Select a valid payment method</span>

![](https://cdn-images-1.medium.com/max/1600/1*VtSSl-GXp7Ms8OFTRErJPw.png)
<span class="figcaption_hack">Confirm your details</span>

Please note that the buttons don’t give any visual feedback of progress. You’ll
need to check Etherscan. We’re working to fix this ASAP.

*****

### 8x.js

Developer innovation is integral for adoption. That’s why we’ve also created a
Javascript library to interact directly with the smart contracts without having
to understand the underlying architecture.

Here’s how you might create a subscription plan as shown through the docs.

![](https://cdn-images-1.medium.com/max/1600/1*FKmkbmNbhvPFHEVOZVsdnw.png)

Check it out at [https://docs.8xprotocol.com](https://docs.8xprotocol.com/)

*****

That’s a wrap for this post! We’d love for you to try out 8x and let us know if
you have any questions.