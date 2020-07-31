---
title: "BlockRocket at ETH London and the birth of the LoanShark🦈"
articletitle: "BlockRocket at ETH London and the birth of the LoanShark🦈"
description: "LoanShark, a trustless NFT leasing platform"
metadescription: "BlockRocket at ETH London and the birth of the LoanShark🦈"
date: 2020-03-02T00:00:00
tags: ["ethereum", "smart contract", "hackathon", "nft", "loan"]
image: "https://cdn-images-1.medium.com/max/400/1*OQvXIJd-vP8zRXoXrz4j2g.png"
author_name: "James Morgan"
author_thumbnail: "https://miro.medium.com/fit/c/96/96/1*pU0bCzBaLEnySQq0APCjWg.jpeg"
author_description: "Co-Founder of BlockRocket"
layout: blog_post
draft: false
---
LoanShark, a trustless NFT leasing platform

This weekend the team and some of our friends travelled down to [ETH London](https://ethlondon.com) for what was set to be a fun filled, action packed and eventful weekend of hacking. Where some of the most exciting *ETH thinkers* on planet Earth 🌎 converge to discuss and innovate on web3 and decentralised economies.

### The team assembled

Myself, [Andy Gray](undefined) and [Oliver Carding](undefined) headed down from Manchester, meeting the other sharks, [@atkinsonholly](http://twitter.com/atkinsonholly) and Jim, in London that day. The week before the hackathon we had started to flesh out the idea on a shared doc so we had a good idea of what we wanted to build, but didn’t really know how to build it yet.

![Jim, Me, Oliver, Holly and Andy — LoanSharks 🦈](https://cdn-images-1.medium.com/max/2000/1*-cF5XhXhqs7ws3-jW7i71g.png)*Jim, Me, Oliver, Holly and Andy — LoanSharks 🦈*

We hacked until 2am on the first night, slept a bit, and then went hard on the second day. Fuelled by joviality and interactions with the other teams and a vast quantities of coffee, tea, beer and nuts! 🍺

### What is Loan Shark? 🦈

**The use-case
**Imagine getting to the final level of a game and needing a *badass* weapon. Not being able to afford it, you should be able to lease the item for a set period of time and return the item once the boss is slayed. Welcome to pay-as-you go assets!

Imagine an avid CryptoArt collector who has amassed a collection from the dopest crypto artists in the space. Then take a metaverse landlord from Decentraland or CrypotVoxels looking for some killer artworks to use in the opening of a new plot. Well, now the collector can safely lend their NFT for, say, 7 days at a set price knowing that at the end, the artwork is safe and sound back in their wallet.

**How does it work?
**Building on the shoulders of giants we leveraged [OpenZeppelin](https://openzeppelin.com/contracts/)’s solid foundation for token standards such as ERC-20 and ERC-721, built on top [Sablier’s payment stream EIP-1620](https://www.sablier.finance) and harnessing DAI as the payment token of choice.

We have created a proxy contract capable of consuming and holding other NFTs which is itself an NFT. We then allow a user to deposit the NFT and define the conditions of the leasing contract.

Anyone willing to take the lease can then pay the fee (by locking up a deposit amount upfront) which is then streamed back to the lender on a per second basis.

![You are going to need a bigger boat!!](https://cdn-images-1.medium.com/max/2218/1*OQvXIJd-vP8zRXoXrz4j2g.png)*You are going to need a bigger boat!!*

Once finished with the NFT, even if this is early, the borrower can return the NFT, closing the payment stream and handing back control of the NFT to the original lender. As we use a stream, the magic is that if the asset is returned early, *any remaining locked-up deposit amount can be returned to the borrower*.

If the borrower does not return the NFT, once the payment stream is used up, the lender can enforce the “return” of their asset. Also, once the stream is used up, the shark contract reverts all proxied methods, so the NFT returns to it original owner safe and sound.

### We won 🎉

We didn’t actual finish everything what we wanted to show but we did prove its possible and got a simple version working (minus a few tiny 🐛).

We managed to land one of the smaller prizes sponsored by [Pepo](undefined) — speaking to Kevin he has impressed by the utility of the application; one of the five categories they judged on.

Here’s a little tweet storm overview:

<iframe src="https://medium.com/media/6da7dc3ec59e25c779dcbd0de26ec8fe" frameborder=0></iframe>

<iframe src="https://medium.com/media/2210062468e8d3a4abe0924e2e0b08fb" frameborder=0></iframe>

<iframe src="https://medium.com/media/03cf96b4faae8379185aba38836723ee" frameborder=0></iframe>

<iframe src="https://medium.com/media/fe0b7c0cafaecdc627fdf66448e5ac3b" frameborder=0></iframe>

The more we think about it the more we like the idea and believe there are some valid use cases. Others have also reached out about the concept which seems to have been received really positively in the wider ecosystem.

We’ve been chatting a bit about the future of LoanShark today and we may put a little Gitcoin grant up to gauge further opinions and see if there is an appetite for this to be developed into something more solid and production ready.

### The future

More and more things have come to light now and below are some more ideas which may be useful for these types of proxy NFT contracts.

* **Flash loans* ***⚡ 🦈 — Trustlessly rent a NFT to play a single move on a Gods Unchained game.

* **Fake IDs** 📛— NFTs can represent identities, you could lease an identity for single block to gain access to something 🤯

* **NFT Brokers** 🏦 — you can use a broker to lend out your NFTs and they can take a % of the stream

* **Charge your strean**🛥 — interest on your stream using charged particples!

* **Private leasing contacts 🔍** — using [zkDAI](https://zk.money/zkAsset/zkdai) to allow private leasing contracts

* **Multi-token support 💰** — leverage social tokens as payment or even any ERC20 compatible token

* **Attention based streams** 🎲— monthly online subscriptions, access tokens can expire when payment streams stop

* **Extra Security 🔐**—moving your NTFs from cold storage but using the wrapper so you can use them but always retract them if lost/stolen

### ETH London breakdown

The event itself was well organised and the submissions to the hackathon were some of the best ideas I’ve seen for a while.

With over 60% of the attendees from the UK, I was pleased to see such as large Ethereum based community in our home country. [BlockRocket](https://blockrocket.tech) not being based in London it’s sometimes hard to judge what’s happening in Ethereum in the UK outside of the big smoke.

We all came away with a renewed sense of confidence and enthusiasm that the space is moving in the right direction. Along with finding out about lots of new DeFi protocols and hearing some of the ETH 2.0 developments which are being worked on.

![](https://cdn-images-1.medium.com/max/5838/1*jKvOpaR_RT_XE4IDCrSdyA.png)

### Thats a wrap…

We’re still recovering from the weekend and trying to work out what to do with the project but watch this space and please reach out if you want carry on hacking on it or have any questions for the *LoanShark* team.

Email — [hello@blockrocket.tech](mailto:hello@blockrocket.tech)

Twitter — [@blockrockettech](https://twitter.com/blockrockettech?source=post_page---------------------------)

Our submission: [https://devpost.com/software/loanshark-g7ti48](https://devpost.com/software/loanshark-g7ti48)

GitHub : [https://github.com/blockrockettech/loan-shark](https://github.com/blockrockettech/loan-shark)
