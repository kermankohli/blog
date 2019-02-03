---
title: "Smart Contract Security Pt 1 - Re-entry attacks"
date: 2018-03-09
tags: ["ethereum", "security", "smart contracts"]
draft: false
---

In 2015, a platform called Ethereum was launched. What made it special was its ability for developers to write custom code, in the form of smart contracts, that executes on the blockchain.

Since you can’t update or change the code, the costs of making any errors are extremely high when writing smart contracts.

Throughout this series I’ll be talking about some of the biggest smart contract exploits, errors and security vulnerabilities that have taken place over the past few years resulting in $100,000,000’s worth of Ether to be stolen or lost.

May 2016, the fundraiser for a decentralised autonomous organisation (DAO) was initiated in order to govern the Ethereum blockchain and fund new projects.

It starts off with a group of developers writing the smart contract to collect funds and develop mechanisms to allow funders to vote based on their ownership.

Once the code has been developed, funds are raised and people can purchase the amount of ownership they would like to have in the DAO.
After funds have been raised backers can propose how to spend the DAO’s money and other members can vote on the proposal
By the end of the 28 days, the DAO had raised over $150,000,000 worth of Ether from 11,000 backers worldwide.

Although due to one small bug, a hacker managed to steal $55,000,000 worth of Ether from the DAO without any traces of who he might be.

## How did this happen?

Don’t worry if you don’t understand this, you only need to know about 2 lines in this whole code block
Here’s how the hack happened from this simple piece of code:

```function splitDAO(
  uint _proposalID,
  address _newCurator
) noEther onlyTokenholders returns (bool _success) {

  ...
  // XXXXX Move ether and assign new Tokens.  Notice how this is done first!
  uint fundsToBeMoved =
      (balances[msg.sender] * p.splitData[0].splitBalance) /
      p.splitData[0].totalSupply;
  if (p.splitData[0].newDAO.createTokenProxy.value(fundsToBeMoved)(msg.sender) == false) // XXXXX This is the line the attacker wants to run more than once
      throw;

  ...
  // Burn DAO Tokens
  Transfer(msg.sender, 0, balances[msg.sender]);
  withdrawRewardFor(msg.sender); // be nice, and get his rewards
  // XXXXX Notice the preceding line is critically before the next few
  totalSupply -= balances[msg.sender]; // XXXXX AND THIS IS DONE LAST
  balances[msg.sender] = 0; // XXXXX AND THIS IS DONE LAST TOO
  paidOut[msg.sender] = 0;
  return true;
}

```

The hacker ran the “splitDAO” function
Let it execute till the point “withdrawRewardFor(msg.sender)” which essentially lets the hacker withdraw the specified amount of ether from the DAO

However, the program is re-run before it can reach the line of code called “balances[msg.sender] = 0” which would set the hacker’s balance in the smart contract to 0.
In even more simpler terms, the attacker was able to “reenter” the contract before it could finish thus allowing him to drain money from the contract by recursively calling the function.

---

The hack could have been avoided if the balance of the hacker in the DAO was subtracted before the funds were transferred (two lines in the function swapped positions). Not only are smart contracts themselves open to reentry attacks, so are the libraries that power them as code is inherited directly.

Since the DAO hack, the Ethereum developer community is highly aware of reentry attacks in order to ensure the mistakes from the DAO aren’t repeated.

The DAO hack is a perfect example of why smart contract auditing and security needs to be taken seriously and with caution as the stakes involved can be very high.