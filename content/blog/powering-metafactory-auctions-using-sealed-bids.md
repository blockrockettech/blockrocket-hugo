---
title: "Powering MetaFactory 🤖 auctions using sealed bids"
articletitle: "Powering MetaFactory 🤖 auctions using sealed bids"
description: "Private auctions delivered by Web3, PGP cryptography and stable coins 🔥"
metadescription: "Private auctions delivered by Web3, PGP cryptography and stable coins 🔥"
date: 2020-04-23T00:00:00
tags: ["ethereum", "smart contract", "pgp", "web3", "cryptography"]
image: "https://miro.medium.com/max/1000/1*a46q0PwGzVU9WQ0viOE5Hw.png"
author_name: "James Morgan"
author_thumbnail: "https://miro.medium.com/fit/c/96/96/1*pU0bCzBaLEnySQq0APCjWg.jpeg"
author_description: "Co-Founder of BlockRocket"
layout: blog_post
draft: false
---
Private auctions delivered by Web3, PGP cryptography and stable coins 🔥

![[https://metafactory.ai/](https://metafactory.ai/)](https://cdn-images-1.medium.com/max/3920/1*a46q0PwGzVU9WQ0viOE5Hw.png)*[https://metafactory.ai/](https://metafactory.ai/)*

We’ve recently been helping build out the first *genesis* iteration of the [MetaFactory](https://metafactory.ai), working with the team behind the project to explore new and interesting auction mechanics.

[MetaFactory](https://metafactory.ai) are pushing the envelope by exploring new and novel ways to engage in commerce and how to build engaged and loyal communities. The ultimate goal being to foster an engaged, incentivised and happy community which will produce apparel and other items in the metaverse and *real *world.

We have so far explored several concepts which we may be included in the future iterations of the project including sealed bids, vickery auctions, plus curved and bonded sales.

Additionally we explored awesome concepts like [charged particles](https://charged-particles.eth.link/) as well as using NFT’s in novel and interesting ways in conjunction with other crypto economic and governance models. Team [BlockRocket](https://blockrocket.tech/) and [MetaFactory](https://metafactory.ai) come from a blockchain heavy/native backgrounds and our focus is always on leveraging the power of decentralised networks with cryptocurrency focused technologies then adding a big sprinkle of innovation on top!

### What are the requirements?

In the alpha version, we have built a solution which will hopefully provide a simple and pain free way for users to make blind bids to compete in an auction for a limited run of bomber jackets that come with membership rights and a non-fungible token…

At the very core of the problem are several requirements which need to be met, below we listed the high level ones out:

* As a ***platform***, we do not want the user to use anything other than a web3 wallet and to own the chosen currency for the auction.

* As a ***platform***, we want to make it very hard or impossible to read other peoples bids.

* As an ***auctioneer***, I need to be able to read all blind bids committed.

* As an ***auctioneer***, I need to be able to prove the authenticity of a blind bid.

* As an ***auctioneer***, I need to be able to result the auction, drawing the funds from the winning bidders.

* As a ***user***, I do not want other participants to see what I bid.

* As a ***user***, I do not want to overcommit my funds as a consequence of obscuring my true bid.

* As a ***user***, I want to be easily see what I have previously bid.

The interesting point here is that there are many ways to solve this common problem but often they have trade-offs, especially in user experience.

For example, we initially considered running a blind auction where users over commit funds. In this example, a user may bid $50 but escrows $250 in the contract to obscure the true bid. However this pattern creates a number of UX challenges and seems overly zealous, not to mention stopping anyone who only has $50 for participating.

### What did we build?

So, adhering to the assumed guidelines above we amassed our weapons of choice and started to build, our toolset comprising of:

* A [smart contract](https://etherscan.io/address/0x9d2454de493141CcCD06Eba254e95A81D294598C) on Ethereum to store all registered bids

* [PGP](https://en.wikipedia.org/wiki/Pretty_Good_Privacy) (via [openpgp-js](https://github.com/openpgpjs/openpgpjs)) to encrypt the bid so only [MetaFactory](https://metafactory.ai) and the user can view it

* Web3 to facilitate cryptographic data signatures to verify and validate interactions

* [DAI](https://makerdao.com/en/) stable coin cryptocurrency as the payment vehicle

* [IPFS](https://ipfs.io/) public storage to store the encrypted bundles and not pollute on chain block space

The general flow can be seen in the diagram below:

![](https://cdn-images-1.medium.com/max/2000/1*9Cg103KMqeKFsqq_7MD-Ig.png)

First, a user decides on the amount they are willing to pay as well as some sizing and contact information. They then sign the data using their web3 wallet, allowing us to verify the data comes from the account who holds those private keys.

Next, we then encrypt the data using [MetaFactory](https://metafactory.ai)’s public PGP key, this allows only [MetaFactory](https://metafactory.ai) to decrypt the bids. Next we push the PGP payload to IPFS turning a large chunky PGP object into a small 46 character IPFS hash. Finally the user submits a transaction to store their signed, encrypted bid on-chain and into a smart contract.

When going through this process no funds are taken! We do check allowances of the payment token, DAI in this case, asking them to approve the registry contract which will be responsible for resulting the auction and pulling all the funds together at that point in the flow.

Lastly the registry smart contract only allows new bids between two dates, enforcing the time limited nature of this auction.

To result the auction we first extract all bids from IPFS, decrypt them, verify the bidder and the signed payload match, sort them by highest price and date entered. We then check the winners still have the funds to fulfil the bid placed, discounting invalid bids and winners which no longer have enough funds. Once sorted and validated we result the auction by drawing the funds from the winning users and place the funds in the smart contract. The result is ordered list of the winning (and unsuccessful) bids and who placed them.

### Thats a wrap

What we hope we achieved is a slightly novel method which means all users can take part and no user has to over commit funds up front, also hoping to meet the criteria mentioned above. This is a tricky conundrum but we feel this approach is one of the cleanest and fairest while maintaining crucial integrity.

The future of [MetaFactory](https://metafactory.ai) is looking bright and fruitful with so many innovative and community driven and focused ventures on the horizon.

Check out [MetaFactory](https://metafactory.ai) and get involved in first [limited edition sale](https://metafactory.ai) for a chance at winning very special unique item 🌶

Remember to come join their [Discord](https://discord.gg/U3wdre) server to scope out what they are up to and how the experiment is progressing.

Reached out to us at [BlockRocket](http://blockrocket.tech) if you want help to realise your product vision and start building the future of commerce and community with web3.

Website 👉 🌐 — [www.blockrocket.tech](https://www.blockrocket.tech/)

Email 👉 ✉️ — [hello@blockrocket.tech](mailto:hello@blockrocket.tech)

Tweet us 👉🐦— [@blockrockettech](https://twitter.com/blockrockettech?source=post_page---------------------------)

Hope this all made sense, James 👊

![](https://cdn-images-1.medium.com/max/2880/0*h8OmFW6Zmhfbsgfn.png)
