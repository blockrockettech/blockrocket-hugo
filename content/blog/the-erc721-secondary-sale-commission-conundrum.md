
# The ERC721 Secondary Sale Commission Conundrum 😐

TL;DR it’s complicated!

At BlockRocket we build dApps and a fair few of them use non-fungible tokens (NFTs) that follow the ERC721 standard. Once the digital assets are live on the blockchain they can commonly be re-sold on secondary markets (primary being the original sale and minting of the token).

The majority of NFTs currently being traded on marketplaces use transfer functions that do not have any *value *exchange bar the token. Marketplaces can accept value, commonly in Ether, and reconcile payments but the asset exchange is normally the standard approve and transfer pattern.

![Random sales image!](https://cdn-images-1.medium.com/max/2000/1*-xUM4snahDB_qofMAe-sag.jpeg)*Random sales image!*

One feature request that keeps popping up especially from creative based projects is the need for secondary commission on resales. We spoke to [KnownOrigin.io](http://knownorigin.io) community on this topic and they were overwhelmingly in support of vested share in future sales.
> Armin Blasbichler, from TwistedSister.io, commented: “The creators of an artwork should have the implicit right to partake in the appreciation of its value over time, as it is them who brought that value into the world in the first place. Such a model, automated via smart contracts on the blockchain, could open up new revenue streams for the creators and would enhance their agency and independence.”

## The problem(s) 👎

Right now there is one secondary market dominating the space for NFTs (because it is simple and easy to use): [OpenSea](undefined).

Unfortunately, they cannot handle payable transfers yet. OpenSea’s infrastructure currently depends on unrestricted transfer functions. In other words, if you add revenue sharing logic directly into the smart contract, they will not currently pass any associated value (in Ether), therefore, no secondary sales split would occur.
> We asked the Opensea guys to review this document for accuracy. Alex Atallah, co-founder, said “We’re very excited about tertiary sales at OpenSea and we’re working to support them. Reach out to us if you have an interesting use case so we can make sure our solution fits! Tertiary sales on OpenSea will be a great way to compensate creators.”

With [OpenSea](undefined) you can specify to add selling and buying fees direct on the platform (and leaving the logic off the contract) so you can manufacture secondary sales but nothing stops savvy users doing OTC (over-the-counter) deals and cutting the content creator out of the deal. [BoxSwap](undefined) is one such platform for OTC deals on NFTs.

So right now if you really need on-chain secondary sales you need to build your own marketplace on your dApp then you are fully in control but this seems like a backwards step for the overall interoperability of NFTs.

Code is law in smart contracts, so you decide you will bake the logic into the ERC721 token via the *transferFrom *(and it’s *safe* equivalents). Next problem is the two most popular frameworks, [Zeppelin](undefined) and [0xcert](undefined), for extending to architect NFTs do not specify the transfer functions as *payable, *whereas*, *the [EIP](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md) standard does!?

Confused? The reasons for this are discussed here:
[**Consider supporting payable ERC721's safeTransferFrom, transferFrom, and approve · Issue #1015 ·…**
*You can't perform that action at this time. You signed in with another tab or window. You signed out in another tab or…*github.com](https://github.com/OpenZeppelin/openzeppelin-contracts/issues/1015)

It boils down to this nugget from the EIP ERC721 specification (don’t try and read this paragraph while drunk…):

    Mutability guarantees are, in order weak to strong: payable, implicit nonpayable, view, and pure. Your implementation MUST meet the mutability guarantee in this interface and you MAY meet a stronger guarantee. For example, a payable function in this interface may be implemented as nonpayble (no state mutability specified) in your contract.

Sometimes it feels like it is never easy on the Blockchain (but is that why we love it secretly? 😘)

## A solution? ✊

We decided to test out converting a NFT contract to use *payable *transfers like so:

    function transferFrom(address payable from, address to, uint256 tokenId) public payable {
          super.transferFrom(from, to, tokenId);

          if (msg.value > 0) {
            // 10% to creator
            uint256 secondaryShare = msg.value.div(100).mul(10);
            _creatorOf(tokenId).transfer(valueToSend)

            // 90% seller
            from.transfer(msg.value - secondaryShare);
          }
        }

It’s a bit of pain in all honesty, our way of being able to do this was to bring in local copies of the [Zeppelin](undefined) code and adjust the required functions and all the associated interfaces.

It felt hacky 😳, but, all the tests passed so we wrote some additional unit tests to prove secondary sales values were redistributed accordingly 💚.

## Conclusion

This appears a simple objective at first but it soon gets a little complex and there is not much out there about it. It is not currently a solved problem and concessions must be made.

You can extend / adjust well documented libs and implement secondary sales but as [OpenSea](undefined) don’t currently support them you are losing out on large potential sales funnel, and you will more than likely need to implement you own marketplace until they do. Bit of a stalemate really 😐.

In the future the situation will improve as the NFT space matures but for now you will need to pick the *rock* or the *hard place.*

[BlockRocket](https://blockrocket.tech/) are based in Manchester and we help companies with blockchain and decentralised technology. Get in touch!

Email: [hello@blockrocket.tech](mailto:hello@blockrocket.tech)

Twitter: [@blockrockettech](https://twitter.com/blockrockettech)

Products we have built include [KnownOrigin.io](http://dapp.knownorigin.io/), [Nifty Football](http://niftyfootball.cards/), [BlockCities](http://blockcities.co/), and [Crypto Kaiju](http://cryptokaiju.io/)
