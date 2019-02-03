---
title: "Exploring the ERC token standard — Pt 2"
date: 2018-04-25
tags: ["ethereum", "ERC20", "smart contracts"]
draft: false
---

In the last post I wrote, I went over the ERC 20 standard and how it can be used
for token sales, traded on exchanges and stored on a variety of wallets.

Today’s focus of attention is going to be ERC 721.

Crypto is still a relatively young space, filled with speculation and
excitement. Through this movement (if you can call it that), there’s been the
rise of lots of new companies from Coinbase to peculiarities such as
CryptoKitties (http://cryptokitties.co). In case you’re not fully up to scratch,
CryptoKitties is a way for people to buy digital cats on the blockchain (think:
Tamagotchi on the blockchain).

*They recently raised $12M from top VCs in Silicon Valley.*

*****

#### Collectable Games

So how does this link in with ERC 721? Good question. Apart from CryptoKitties
there’s been a large influx of tradable collector games such as
CryptoCelebrities and CryptoCountries.

In these games people might “buy” Bill Gates for 1ETH. Then the next collector
will come along and buy Bill Gates for 1.5ETH. The difference of 0.5ETH is
distributed to the previous owner and game creator.

What all of these games/applications have in common is creating a one-of-a-kind
digital asset that can then be traded. It’s different to a ERC 20 token due to
the fact that it represents ownership of a rare, unique collectable (kind of
like collectable baseball cards).

It’s for this reason that a standard for creating collectable assets that can be
traded was created.

*****

#### ERC 721

All of these standards simply define an interface which can then have their own
implementation. A use case for this may be a platform which allows players to
compare/brag about their digital ERC 721 collectables on a single platform.

Here’s the full code for an ERC 721 interface:

    contract ERC721 { 

    // ERC20 compatible functions 
    function name() constant returns (string name); 

    function symbol() constant returns (string symbol); 

    function totalSupply() constant returns (uint256 totalSupply);

    function balanceOf(address _owner) constant returns (uint balance); 

    // Functions that define ownership 
    function ownerOf(uint256 _tokenId) constant returns (address owner); 

    function approve(address _to, uint256 _tokenId);

    function takeOwnership(uint256 _tokenId); 

    function transfer(address _to, uint256 _tokenId); 

    function tokenOfOwnerByIndex(address _owner, uint256 _index) constant returns (uint tokenId); 

    // Token metadata 
    function tokenMetadata(uint256 _tokenId) constant returns (string infoUrl); 

    // Events 

    event Transfer(address indexed _from, address indexed _to, uint256 _tokenId); 

    event Approval(address indexed _owner, address indexed _approved, uint256 _tokenId);
    }

Didn’t understand any of the above? That’s aright, because I’ll be breaking it
down below.

* `Name` — settable name such as “My Collectable Token” defined in the smart
contract
* `Symbol` — short abbreviation used for the collectable (eg “MCT”), similar to
ERC 20 tokens
* `Total Supply` — how many collectables of this family exist. This may be subject
to change.
* `Balance Of` — how much of that collectable does someone own
* `Owner Of` — find out who is the owner of a token (where token could be a
CryptoKitty/Country/Celebrity/etc.)
* `Approve` — approve the transfer of an asset to another address/person
* `Take Ownership` — another user can take ownership of an asset from another user
only if they’ve been approved (see above)
* `Transfer` — send the token to another party, although the receiving party must
have been approved in order for the transfer to work
* `Token Of Owner By Index` — since each token has it’s own unique ID, this method
allows someone to view all the tokens held by an address/person
* `Token Metadata` — unique data about a particular token (colour of your kitty,
characteristics of the country you “own” etc.)

The `Transfer` and `Approval` events simply notify relevant parties that a
change in ownership has occurred or that an approved owner has been added.

Hope you found value from this! Would love to hear your thoughts and any
comments you may have!
