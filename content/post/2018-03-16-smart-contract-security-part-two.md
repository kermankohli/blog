---
title: "Smart Contract Security Pt 2 - Library Dependency"
date: 2018-03-16
tags: ["ethereum", "security", "smart contracts"]
draft: false
---

Gavin Woods, Ethereum’s co-founder and CTO, created a non-profit organisation called Parity Technologies in order to develop software for the Ethereum blockchain. One of their first products, Parity, was a client that allowed users to store their Ether and also interact with block chain smart contracts.

Some of the Parity’s functions relied on a multi-signature smart wallet library (created by the Parity team) to store funds. In case you didn’t understand what a “multi-signature wallet” was, it’s basically a wallet which needs authorisation from multiple users in order to make any decisions such as sending funds. The practice of separating logic is usually good practice. In fact, many modern developers rely on libraries in order to speed up development or to use functionality that would be hard to develop by themselves (ie. cryptography with lots of maths).

---

Since libraries are smart contracts at the end of the day, any mistakes made are unchangeable and will be used by applications using that sepcific library.

In the case of Parity, they developed their smart contract multi-signature library although with one error — there was no owner set for the wallet once it was deployed. It wasn’t long until someone by the name “devops199” initialised the contract and set himself as the owner (since there was none before that). Since there was only one owner signature in the wallet, he was now in control of all the funds stored in the library. With great power comes great responsibility, unfortunately in this case it was used with irresponsibly.

Devops199 then went on to proceed to call the following code:

```function kill(address _to) onlymanyowners(sha3(msg.data)) external {
    suicide(_to);
}```

In case you didn’t understand what that code means:

The first line is defining the function to kill the contract. However it can be called by “onlymanyowners” (in this case the hacker being the only owner) and can be called externally (outsiders).
The second line is the suicide function, which kills the library and locks up all the ether stored in it!
Now, any wallet which tried to access its funds would be presented with an error since the library was dead, as well as their funds.

A screenshot of the hacker who claims to have “accidentally” killed the contract. He says his intentions were not harmful, although his actions suggest otherwise. 

> Source: https://github.com/paritytech/parity/issues/6995

### Post mortem
This exploit effectively destroyed 1% of the circulating supply of Ether forever and costed hundreds of addresses over $150M collectively.

While the hacker was the one who pulled the trigger to the exploit, majority of the responsibility lies in the hands of the Parity team who claimed to have had the contract thoroughly reviewed.

Due to the outrage of the community, discussion of a hard fork began. Although due to the consequences (as shown with Ethereum Classic and Ethereum) this was promptly ruled out. The ultimate resolution of the drama resulted in the funds being locked up forever.

An external audit from one or multiple parties could have prevented this attack as audits are done line by line.

CanYa’s Bountysource platform in the future will allow smart contract developers to post their code in order to check for any security exploits. In addition, Bountysouce also has lots of other updates in the pipeline such as a new interface and more features on their development roadmap!