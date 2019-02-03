---
title: "Exploring the ERC token standard — Pt 1"
date: 2018-04-04
tags: ["ethereum", "ERC20", "smart contracts"]
draft: false
---

You’ve may have recently wondered how everyone’s able to create their own crypto
currency? From StrayaCoin to PonziCoin there’s no shortage of coins out there.
What most people don’t realise is a lot of these coins are based on a standard
called ERC20.

*****

### Why have standards?

Standards, in technology, allow programs to communicate in a certain way
regardless of they way they’re implemented. The most common standard across the
web is TCP/IP, the way in which data is transferred for the internet to
communicate. It doesn’t matter what data you send, as long as it uses TCP/IP
another device will be able to read the incoming data and understand it
accordingly.

*****

### What is ERC?

ERC stands for Ethereum Request for Comment. In order to create a new standard,
developers need to submit an Ethereal Improvement Proposal. Once this been
approved and finalised by a committee it becomes ERC compliant.

*****

#### Cryptocurrencies and ERC20

ERC20 is the common standard for all token sales or ICOs that come out these
days. By being an ERC20 token, exchanges, hardware wallets and other systems can
immediately support the coin. This is due to the widespread adoption of ERC20
over the past year since it’s release in September 207.

The ERC20 standard has the following variables and methods as part of its
interface:<br>  — Total supply: how many token exist in total<br>  — Balance of:
returns the balance of a specified owner<br>  — Transfer: permits the transfer
of tokens from one user to another

There’s another 3 methods related to transferring tokens on behalf of another
address which are shown in the code snippet below.

A full ERC20 interface looks like this in case you were wondering:

    contract ERC20 {
     // Transfer tokens to an address with a specified amount
     function transfer(address _to, uint256 _amount) returns (bool success);

    // Transfer from an address, to another one with a specified amount
     function transferFrom(address _from, address _to, uint256 _amount) returns (bool success);

    // Return the the number of tokens a particular balance holds
     function balanceOf(address _owner) constant returns (uint256 balance);

    // Approve an address to spend a certain amount for you on your behalf
     function approve(address _spender, uint256 _amount) returns (bool success);

    // Specify an allowance for another to spend up to
     function allowance(address _owner, address _spender) constant returns (uint256 remaining);
     function totalSupply() constant returns (uint);
    }

Most ERC20 tokens used for token sales also include a name, symbol and decimal
points supported (typically 18). If I was to create my own personal token it
could be called “Kerman Coin” with a symbol of “KERM” and support up to 1/18th
of a unit. It could then immediately be supported by crypto exchanges and
software wallets.

Currently, the following large platforms/wallets support ERC20 tokens:<br>  —
MyEtherWallet<br>  — Trezor<br>  — Nano Ledger S<br>  — Parity<br>  — Metamask

### What’s next?

There’s many more ERC standards supporting different use cases. The next few
articles will go into detail about them.

Bounty Source is a platform that helps companies find bugs in their open source
code. They’re currently working on providing support for Ethereum smart
contracts.
