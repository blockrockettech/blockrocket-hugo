---
title: "Tokenlandia - Certificates of Authentication For All Your Purchases"
articletitle: "Tokenlandia - Certificates of Authentication For All Your Purchases"
Description: "A dive into the NFTs and infrastructure built by BlockRocket"
SubDescription: "A dive into the NFTs and infrastructure built by BlockRocket"
metadescription: "A dive into the NFTs and infrastructure built by BlockRocket"
image: "/images/TokenlandiaLogo.png"
tags: ["blockchain", "smart contract", "ethereum", "nft", "erc721"]
layout: use_case
---

<img src="/images/TokenlandiaLogo.png"/>

### About the Project

[TokenLandia](https://www.tokenlandia.com/) and its sister company VideoLatino are aiming to be the go to place for trusted, blockchain authenticated, 
merchandise and physical goods store. 

They provide authenticated and verified high end clothing and other goods which can be purchased using fiat and crypto currencies,
where the buyer will also receive a tradable proof of authenticity in the form of a NFT. 

### Implementation

Behind the shiny ecommerce website we have built a suite of smart contracts, back office administration tools as well as a 
transaction APIs which abstracts away the blockchain from Tokenlandia and the ecommerce side of the platform. 

#### Smart Contracts
 * A suite of upgradable token (ERC-721) contracts which are responsible for providing the proof of purchase and authenticity.
 * Esrcow and management tools for back office administration of tokens

#### IPFS (Interplanetary file system)
 * All meta-data is public
 * IPFS is used to host all data associated with the digital assets including images, names, descriptions
 * A peer-2-peer decentralised open network for sharing files

#### Transaction API
* Responsible for creating, moving and issues NFTs 
* Removal of the need for `GAS` for customers and back office staff
* Batching and queue logic to ensure transaction are processed in order and in time

### Outcome
TokenLandia are nearing launch where they are looking to drive new standards and customer expectations
 when purchasing genuine and verified goods.
