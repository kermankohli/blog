---
title: "Blockchain — isn’t it just a scam with lots of hype?"
date: 2018-01-24
tags: ["blockchain", "cryptocurrency", "intro", "bitcoin"]
draft: false
---

Being someone who’s in the tech industry, I’ve been hearing about the blockchain since 2015, but I never really gave much attention to it since I couldn’t really see what the big deal was.

Decentralised? Immutable? Distributed ledgers? So what?

This “so what” attitude changed for me when I met up with someone who described disruption something like the image below.


By the time you realise the tech isn’t disappointing it’s already way too late.

We’ve seen this countless times in history. Here’s snippets of criticism regarding the internet in 1995 and the iPhone in 2007:

`Then there’s cyberbusiness. We’re promised instant catalog shopping–just point and click for great deals. We’ll order airline tickets over the network, make restaurant reservations and negotiate sales contracts. Stores will become obselete. So how come my local mall does more business in an afternoon than the entire Internet handles in a month? Even if there were a trustworthy way to send money over the Internet–which there isn’t–the network is missing a most essential ingredient of capitalism: 
salespeople. — https://thenextweb.com/shareables/2010/02/27/newsweek-1995-buy-books-newspapers-straight-intenet-uh/#.tnw_92YdWL7k`

`[The] iPhone crams too many functions into a single box. Putting everything in the same package so you only have to carry one box sounds like a good idea, until you want to listen to music while surfing the web or reading your email or playing a game. Then users will find it essentially impossible to use one function of the tiny box without disrupting the operation of another. A few dedicated technophiles might, just MIGHT, figure out how to do so, but it will require far more dedication than an ordinary user is willing to invest in learning and then remembering. — http://bgr.com/2016/07/01/iphone-reviews-original-negative-ballmer-dvorak/`

Almost everyone expects the future to be a slightly modified version of the present, but it’s usually very different — Ray Dalio
Before I dwell into what the blockchain is, it’s worth exploring the reasons behind why cryptocurrencies (the first & most well known application of blockchain) came to existence.

When I asked my 16-year-old sister about what she thought about bitcoin our conversation went a little something like this:

    Me: “What do you think about Bitcoin?”
    Sister: “Isn’t it just a scam where people are trying to make money?”
    Me: “Why do you think it’s a scam?”
    Sister: “Because it has no real value.”
    Me: “Do you think money has value?”
    Sister: “Yes, because it’s linked to gold.”
    That last line is where things get interesting. Money is one of the most fundamental concepts of society yet we don’t fully understand it.

## What is currency?
Before we begin it’s worth examining the properties of a currency:

- Scarce — limited supply and highly sought after
- Fungibility — the symbol should be interchangeable (it doesn’t matter if you call it “cash” and I call it “dollars” since it refers to the same thing)
- Divisibility — it can be divided into smaller portions
- Durability — can survive over time and won’t deteriorate
- Transferability — ability to easily be transferred between owners
Now let’s go back a few thousand years.

I have a goat and you have a cow. We end up bartering what we have with what we want.

Now obviously this gets problematic if the goods we’re trading aren’t scarce (or I don’t have a need for it), divisible (I can’t trade 0.002 of a goat), durable (your cow will die in the near future) and transferability (will need equipment to move around the animals).

So what did us humans do? We agreed on a common exchange of value. This took forms such as seashells, food, stones and more. Ultimately we converged to rare earth metals such as bronze, silver and gold as the standard exchange of value.

Fast forward a few thousand years till we reach the 1970’s.

If I went to the bank, I could exchange my $35USD for 1 ounce of gold. Unless I could mine lots of gold (which is extremely hard) I knew that supply was limited and there was extrinsic value to my paper dollars. This all changed in 1971 when the US government ended it’s adherence to the gold standard internationally in order to finance the needs of the country. Now, if there wasn’t enough money to pay for things the government could simply print more.

My $1,000 USD worth of goods in 1971 would end up costing $6,000 USD in the year 2016 from an inflation rate of 505% (source: http://www.usinflationcalculator.com/). Meaning if I held onto $1,000 USD in 1971 it’d now be worth ~ $166 in relative value.

So going back to the question about whether money has value — not really. It’s primary value is from the fact that everyone in the world will accept some form of dollars (USD, AUD) to exchange value (goods and services).

## Introducing Bitcoin
In 1982, a man named David Chaum created the first cryptocurrency called ecash. It used advanced cryptography techniques from it’s time in order to securely manage and transfer ecash between participants. The parent company DigiCash eventually ran out of funds and had to cease operations. This highlights the dangers of centralisation — it only takes one blow to take the entire network down (bankruptcy, regulation, security flaws etc). The internet is an example of a decentralised system, no one owns it and cannot be “shutdown”.

A solution to a decentralised cryptocurrency came in 2008 when Satoshi Nakamoto (we don’t know who he actually is) created Bitcoin. He achieved this through advanced cryptography techniques and solving a combination of many computer science problems such as byzantine fault tolerance which ensure a network of distributed systems (some of which may be dishonest/malicious) can reach consensus (aka agree on the same thing).

Bitcoin contains all the properties of a currency and is scarce since there can only ever be 21 million in existence.

## So how does it work?
Each transaction made is broadcasted to a network of “miners” (anyone can be a miner)
Miners collect a limited number of transactions till a “block” is formed. In order to validate this block they need to solve an extremely hard math problem before any other miner does (by guessing and checking). The probability of getting this correct is ~ 1/1,000,000,000,000,000,000,000. It’s also worth noting that the amount of resources (electricity, hardware, time) to mine these blocks is extremely high.
Once the problem is solved, miners receive 12.5BTC (worth ~$120,000 at the time of writing) for “mining”/validating that particular block. The new block is broadcasted to the entire network and everyone adds the latest block to their own copy of the blockchain. If a hacker tries to create a block with fake transactions he’ll need to mine faster than 51% of the entire network to validate his fake blocks (which is extremely hard to do and not economically profitable). Blockchain technologies are designed in such a way that the most profitable strategy is through honesty.

Ultimately every participant in the network has their own version of the blockchain and they listen for validated blocks to be added to it. This is what it means to have a decentralised (isn’t owned by a single person), immutable (cannot be changed/doesn’t make sense to) and distributable ledger (everyone has the same copy).

Returning back to where we started, does Bitcoin have any “extrinsic” value except for the amount of energy required to keep the system alive — not exactly. Although unlike fiat currencies, more Bitcoins cannot be produced out of thin air. As long as everyone agrees that its an exchange of value (or will be in the future), it retains its value.

In the world of the internet, trust is a commodity that is extremely hard to earn and even harder to retain. Every centralised organisation has it’s own points of failure that can have disastrous consequences if compromised. The blockchain safeguards us against these centralised points of failure.

While I haven’t dwelled into the other uses of blockchain (next post), I hope you were able to get a decent understanding of what it’s all about and why there’s so much excitement around it!