---
title: "Scaling Ethereum — what scaling solutions can you use today? | Blog | BlockRocket.tech"
articletitle: "Scaling Ethereum — what scaling solutions can you use today?"
description: "Scaling Ethereum — what scaling solutions can you use today?"
metadescription: "Scaling Ethereum — what scaling solutions can you use today?"
date: 2019-05-07T00:00:00
tags: ["artificial intelligence"]
image: "https://miro.medium.com/max/3334/0*NQhtdlGciXgQEvas.png"
author_name: "James Morgan"
author_thumbnail: "/images/James.jpg"
author_description: "Co-Founder of BlockRocket"
layout: blog_post
draft: false
---
# Scaling Ethereum — what scaling solutions can you use today?

How projects can leverage the latest scaling technologies to build highly scalable Ethereum applications

![credits to district0x — [https://education.district0x.io/general-topics/](https://education.district0x.io/general-topics/)](https://cdn-images-1.medium.com/max/3334/0*NQhtdlGciXgQEvas.png)*credits to district0x — [https://education.district0x.io/general-topics/](https://education.district0x.io/general-topics/)*

At BlockRocket we are often asked by clients, how can they can leverage public blockchains like Ethereum without suffering from known blockers such as scalability and transactions costs.

Today, the Ethereum ecosystem is maturing and scaling solutions, also known as layer 2 solutions (L2), are becoming *production ready*. We have been building with a variety of tools and frameworks that now allows us to advise our clients on the best approach right now on what can be realistically done and where we see this technology going.

Scalability always has trade-offs in relation to network security, complexity, operational costs, UX challenges, transaction throughput as well time to build. These decisions and trade-offs need analysis as there is no one-size fits all solution. We aim to present the full range of options and trade-offs to our clients helping them make the right choice to allow them to use the power of blockchain without stifling business growth and adoption.

Below we will be covering some of the options available to the market.

## The Status Quo

In the not so distant future ETH 2.0 will come alive, powered by a transition to proof-of-stake consensus mechanism, and teams and projects will be able to tap into much higher levels of throughput natively. Until then we need to build products which work today and with the future in mind.

### Running on *Mainnet*

Ethereum is without doubt one of the most popular and most powerful blockchains for decentralised applications. There are approximately 9000 nodes participating in the upkeep of the network according to [ethernodes](https://www.ethernodes.org/), and thousands of engineers and teams building on it.

It is a well known fact that public proof-of-work blockchains do not scale very well *at the moment*, currently processing approximately 15–20 transactions per second which can be a problematic for businesses entering the space.

Unfortunately, the volatility of transaction costs also causes financial planning nightmares.

This has driven demand, research and the subsequent rise of layer two scaling solutions, aiming to deliver higher throughput and lowering transaction costs, enabling businesses to participate in this nascent and emerging field without penalties or friction.

## Scaling Ethereum Today

We will break down these options into broad camps based on type, touching on some of the more interesting parts of each. Our focus will be on how to scale public Ethereum. We will not be touching on things like lightning network, liquid or Rootstock which represent some of the advances on alternative networks such as Bitcoin, these would require a full post in their own right.

### Sidechains

Sidechains fall under two broad categories themselves, *generalised sidechains* or *application specific sidechains*. Application specific sidechains being the simpler of the two solutions to build and have been around for many years.

![](https://cdn-images-1.medium.com/max/2000/0*R9eLfDHjpqbsmpOv.jpg)

Application sidechains often greatly sacrifice decentralisation and require users to trust the operators which run them. For example a dApp may host and run a bespoke solution that naturally can create a vendor lock-in scenario. Additional complexity and understanding is required to connect users and their wallets to the sidechain.

Generalised sidechains, such as [xDai](https://poa.network/xdai)/[POA](https://poa.network), are the newer kids on the block and have been put into use on successful proof-of-concepts such as [Austin Thomas Griffith](undefined)’s [burner wallet](https://github.com/austintgriffith/burner-wallet) and the [Geon Network](undefined) geocaching application. They provide large improvements in throughput without sacrificing richfullness. Are relatively simple enough to build on as they are near identical clones of Ethereum.

Users deposit coin or tokens into the smart contracts on mainnet, once deposited the assets are locked and moved to the sidechain, they can then transact freely at great speeds and lower costs.

POA/xDai use a consensus mechanism called proof-of-authority, coming to consensus using a smaller authoritative and legally bound nodes. Through federation higher scale is achieved with reduced blocktimes (5 seconds). Crucially xDai’s native currency as DAI, a US pegged stable coin, which enables much better operational planning and understanding as token *swaps* are not required and mentally users naturally understand this fiat peg to the world’s primary currency: USD.

In general we are big fans of POA/xDai concept — it's an easy transition for a development team to build on, simple to forecast upon, and has mature tooling and documentation. We would however be reluctant to lock up very large monetary volumes in the network right now, as theoretically, there is a possibility of node collusion and censorship due to the smaller number of operators. That being said, we see these type of solutions suit certain types of projects who may use sidechains as stepping stone. Migration to and from POA style Ethereum chains should be simple ensuring projects are not tied to one scaling solution permanently and can be ported if the need be.

### Generalised State channels

State channels, often called payment channels, are not a new concept and conceptually underpin things like the [lightning network](https://lightning.network/) on Bitcoin and the [Raiden Network](undefined) on Ethereum.

![[https://education.district0x.io/general-topics/](https://education.district0x.io/general-topics/)](https://cdn-images-1.medium.com/max/5200/0*KKmpmb7q1BNVt3jh.jpg)*[https://education.district0x.io/general-topics/](https://education.district0x.io/general-topics/)*

What we have seen in Ethereum over the last few years is the fruition of generalised state channels, allowing any application to tap into and use these for more than just payments but for generalised smart contract state.

At a high level, state channels follow a similar pattern to most layer 2 solutions. Users lock up assets in a smart contract on mainnet, once locked they can transact on a state channel, *exiting* the state channel to mainnet when complete.

Users transact *off-chain* by passing incrementing states between each other which represent balances. The most recent balance can be used at any time as an *exit transaction* to leave the state channel to return to the main chain.

State channels have been leveraged by products such as [mosendo](https://mosendo.com/), [Ujo Team](undefined), [SpankChain](undefined). More recently [MetaMask](undefined)’s mobile app now natively includes a DAI <> ETH state channel implementation called DaiCard — allowing for near instant and free dai transfers between users.

Traditionally payment channels lack the ability to run arbitrary smart contracts and are really designed to allow for assets transfers such as ERC20 and ERC721 however state channels are evolving to offer generalised off-chain smart contract interactions as well.

Free, or near free, fast transfers between parties are awesome however this often leads to a higher operational costs for running state channel hubs infrastructure that may require to maintain large amounts of state. They also don’t *yet *facilitate interoperability between different state channel provider hubs, meaning that those hubs are required to be highly available and robust, *if the hub is offline you will not be able to transact*. Another benefit is perceived privacy improvements as transactions are not broadcast publicly and they occur between parties.

Undoubtably, state channel solutions by [Celer Network](undefined), [Counterfactual](undefined) and [Connext](https://connext.network/) do offer substantial improvements in cost and transaction throughput over operating directly on the main chain. Channel exits and exit *proofs *remain an education challenge and point of friction that needs to be better understood for greater adoption.

They do represent a more complex solution than a sidechain, mentioned above, and will add costs in regards to development time but they do typically offer well documented and feature rich simple SDKs and APIs to help with this. They have also been more battle tested than solutions like Plasma and are in production use by several projects around the world.

We would advocate the use of state channels when businesses require to transact assets in large volumes a.k.a. micro-payments. They represent a common solution to a common problem as long as the trade offs are understood. They are without a doubt a solid solution for businesses which operate as the middleman or hub facilitating interactions between its users.

### Plasma

[Plasma](https://plasma.group/) is a newer bread of scaling solution aiming to provide a trust minimised alternative to state channels and sidechains. They heavily rely of cryptography, cryptoeconomic incentives and game theory to provide a solution which is completely trustless and has greater decentralisation. Interestingly plasma solutions such as [Matic](undefined) leverage proof-of-stake side chains as well to reduce the ability to censor or collude as a Plasma provider.

![](https://cdn-images-1.medium.com/max/2000/0*23VuLoOWitXryxQN.png)

Plasma relies on merkle proofs submitted to the main chain by the validator so users must still wait for confirmations in order to consider their transactions complete and final. There is also a concept commonly called *watch towers* which are required to ensure that when malicious actors attempt to cheat or if another party is offline, the watch tower will ensure that fraud proofs are correctly submitted to combat this malicious behaviour.

They reduce some of the issues of state channels in that funds are not custodially held, can always be recovered and malicious plasma operators do not have the opportunity to steal funds. They present the very bleeding edge of the scaling debate on Ethereum and in our opinon still have work to do in regards to bringing these type of technology to the developer masses. Plasma implementation also currently have long *exit* games initiated when users leave the plasma chain and move to the root chain, this can also be problematic for application developers in terms of UX.

Plasma represent a viable scaling option and should be used when necessary. There is most definitely an increased level of complexity and costs to be had from utilising these solutions which should reduce over time as products and services mature.

### In conclusion

To wrap up, I hope the above has given you an insight into the current options which are applicable to projects which need to leverage higher levels of scale.

All options have trade-offs in some form so each application of them needs to be assessed based on the requirements of the project themselves.

In the future we will see these tools mature even further and we are confident that the challenges touched on above can be resolved as adoption grows.

If you want to speak to us directly about how to leverage these tools please reach out to us using the links below.

Website —[www.blockrocket.tech](https://www.blockrocket.tech/)

Email — [hello@blockrocket.tech](mailto:hello@blockrocket.tech)

Twitter — [@blockrockettech](https://twitter.com/blockrockettech?source=post_page---------------------------)

Check out our community meetup for our up and coming events — [Blockchain Manchester](https://meetup.com/BlockchainManchesterMeetup?source=post_page---------------------------)

**If you enjoyed this post please show it some ❤️ and give it a clap of 50 👏👏👏— James**

For more high level info on the topics above take a look below:

* [https://plasma.group/](https://plasma.group/)

* [https://education.district0x.io/general-topics/understanding-ethereum/basics-state-channels/](https://education.district0x.io/general-topics/understanding-ethereum/basics-state-channels/)

* [https://education.district0x.io/general-topics/understanding-ethereum/understanding-plasma/](https://education.district0x.io/general-topics/understanding-ethereum/understanding-plasma/)
