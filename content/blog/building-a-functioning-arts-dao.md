---
title: "Building a functioning arts DAO"
articletitle: "Building a functioning arts DAO"
description: "Our take on the components required to build a profit seeking DAO that curates and sells NFTs"
metadescription: "Our take on the components required to build a profit seeking DAO that curates and sells NFTs"
date: 2019-11-09T00:00:00
tags: ["dao ethereum smart contracts art"]
image: "https://miro.medium.com/max/3705/1*ixxMNvSU0111U-nH9Mxjag.png"
author_name: "James Morgan"
author_thumbnail: "https://miro.medium.com/fit/c/96/96/1*pU0bCzBaLEnySQq0APCjWg.jpeg"
author_description: "Co-Founder of BlockRocket"
layout: blog_post
draft: false
---
Our take on the components required to build a profit seeking DAO that curates and sells NFTs

![](https://cdn-images-1.medium.com/max/7410/1*ixxMNvSU0111U-nH9Mxjag.png)

After our recent launch of the experimental DAO, [Osaka DAO](https://knownorigin.io/dao-osak), it soon became apparent that even with all the current DAO hype, there still isn’t the right sort of DAO aimed at creative curation and revenue generation that aspires to be profit seeking. Although it is in the name most current implementations are not very autonomous!

This got us thinking about what would it take in order to build a DAO that can fulfil these requirements. The main elements needed are as follows:

* ***Raising funds:* **Ability to *commission* creative content into existence

* ***Curation:*** Allow members to vote on proposed artworks

* ***Creation:*** Trigger the minting the NFTs on passed proposals

* ***Remuneration:*** Increasing share value from the sales of the artworks

* ***Engagement:*** Shareholders are incentivised to get involved at all stages

* ***Visibility:* **How it all works and what state we are currently in

Some of the above areas would require significant changes to the current gold standard of DAOs, [Moloch DAO](https://molochdao.com), but if undertaken in our mind would facilitate a DAO which can curate, mint and raise profits from the sales of NFTs autonomously.

Our thinking has been based around how would this work with [KnownOrigin](http://knownorigin.io), mainly as it’s our product and we know how it works inside and out but in theory this could be applied to other projects, maybe even some standards could fall out the back of this for others to use.

## A future path for KnownOrigin
> One outcome we would like to see is having a permanent curator on KO which is actually a DAO.

We can accredit the artwork to the original artist but having the curation and submission happen from the DAO itself would be a pretty unique and innovative situation. The share holders then influence the direction of the platform not the centralised team running KnownOrigin!

This would mean that artists could submit proposals to the DAO for commissions for future artwork, the DAO would vote and issue shares for proposals (that can be exchanged for cryptocurrency), once accepted the DAO would mint the NFTs and sales revenue would be feed directly back into the DAO’s bank. Making the DAO a fully autonomous operator where the members decide on the creative output and gain share value on any sales generated.

We think that in a decentralised world, where crypto art is created and listed from all over the world, having a DAO drive this process seems like an obvious and natural fit. The million dollar question is can survive and thrive for any prolonged amount of time autonomously is however unknown.

## Raising funds
> ***Problem:** What are the legal implications for having a profit seeking DAO using NFTs as the vehicle for raising funds?*

Raising and distribution of funds is the bread and butter and backbone of most DAOs. This does however raise more questions: legal questions — is this a security? Probably Yes.

[OpenLaw](https://www.openlaw.io/) ([OpenLaw](undefined)) seems to be making strides in this arena and is something which needs further investigation. Also we are really talking about a LAO (A For-Profit, Limited Liability Autonomous Organization) not a DAO!
[**The LAO: A For-Profit, Limited Liability Autonomous Organization**
*OpenLaw will be launching the first limited liability for-profit DAO, named the LAO. The LAO will enable members to…*medium.com](https://medium.com/openlawofficial/the-lao-a-for-profit-limited-liability-autonomous-organization-9eae89c9669c)

In a nutshell though, we need a DAO structure that can raised funds, funds can be used to produce creative content, selling the assets raises revenue that can be fed back into the organisation potentially created a profit.

## Curation
> ***Problem**: Currently Moloch a based DAO demands only one vote to accept a proposal, this may not work for curated art, I believe a form of voting rounds or minimum number of votes would probably be ideal for our situation. Or even a max number of accepted artworks per day for example. One advantage of a curation, fund directing DAO is in the selection power and opinion of the crowd.*

In our experiment, we internally and manually went through a voting process which whittled down the 30 submissions to 8. We know this isn’t right but time and functionality constraints forced our hands.

What we really need is the ability to allow the artists, who would need to be members of the DAO, to submit proposals with all the required data attached for generating an NFT after the proposal goes through.

Other more interesting options exist which could leverage some form of reputation or other on-chain voting mechanics. Exploration of these could come with time and once we know how the DAO operates.

## Creation
> ***Problem: **Different platforms have different technical requirements for minting NFTs. Although it’s technical possible to handle multiple via clever smart contract designs, it will increase complexity and add security risks.*

Enabling a DAO to mint artwork on KnownOrigin is not such a hard task however making the DAO generic enough to mint on all or multiple platforms will take time.

Another possible problem is who is responsible for the DAO? If the DAO mints work which is fraudulent, a copy or is illegal in some form. Is it the DAO or the platform where the NFT is minted responsibility?

New standards are really needed for this to work on a larger scale. In the meantime we will start to look at how this will work on KnownOrigin, reach out if you have ideas on how this would work.

## Remuneration
> ***Problem:** Reconciliation of sales against proposals is hard, if this was in place it could lead to some interesting observations and analytics on how well the DAO is performing, maybe even influencing future proposals or share offerings.*

By default all smart contracts can be sent Ether or tokens direct, however doing so using standard patterns means it would be very difficult or impossible to know what artwork any generate revenue was derived from.

Another option would allowing sales could generate new proposals to that can be tracked and voted back into DAO (and the underlying bank)

The reason this is required for our use case is that the commissioning DAO needs to be rewarded in the form of sales for its work. In essence the DAO is the collective commissioner, the curator, the minter and should also be the recipient of the sales values in reward for this.

## Visibility
> ***Problem**: DAOs are still too technical and complicated for those outside of the crypto savvy and tech focused circle. We need a simple overview which presents and user friendly and simple to use DAO dashboard with basic functionality.*

Vote apathy kills DAOs. Visibility and simple tooling is the easiest way to fight against this.

We have already made some progress by building a simple dApp which provides basic functions and and more detailed overview of the current situation. [https://thedogsmolochs.blockrocket.tech](https://thedogsmolochs.blockrocket.tech)

Its fully open source, easy to deploy which someone has already done!

<iframe src="https://medium.com/media/49b88c5decb7c8392cd924a9e33c1cbf" frameborder=0></iframe>

We will continue to improve this with the goal to provide a simplified view of the current state of DAOs. Fork the code, add some logic, open a PR if you want to get involved [https://github.com/blockrockettech/the-dogs-molochs](https://github.com/blockrockettech/the-dogs-molochs)

## Engagement
> ***Problem:** DAO Osaka and many DAOs have long periods between voting and proposals. Longer times reduce engagement, lead to voting apathy and mean proposals and or votes are missed.*

From our small experience in the DAO space, it feels like we need shorted time periods between voting and proposing. There are game theoretical reason for longer times but I think we can reduce these times to hours or even 1–2 days instead of several days between them. Rage quit means those who don't agree will still be able to exit when not happy.

## What's the point of all this?

Building the above would be both beneficial to KO and the wider ecosystem in my opinion.

**I would like to see a viable circle of value creation, artwork creation with proper and suitable remuneration for the artists.**

I would like to see those who are passionate and committed to the crypto-art space fund the creation and subsequent profit making from art as the space continues to grow.

We love crypto and we love art, throw in some collective decision making and the opportunity to make some money and I think we have a very attractive proposition.

## Wrapping up

I’d love to hear feedback on how those that participated in DAO Osaka and from those that may or may not think this is possible.

Would like to collaborate on this venture? Do you know some of the solutions to the problems raised above?

For now we will carry on hacking away and promote the space as much as we can.

Leave your thoughts below if you have anything to add.

Peace out

James & the [KnownOrigin](https://knownorigin.io) team
