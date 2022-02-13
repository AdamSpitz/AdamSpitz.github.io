---
layout: post
title:  "Leftie-friendly crypto projects"
date:   2022-02-13
---
There are things I'd like to say about how crypto has some potential for reducing the polarization between left-wing and right-wing people.

I think a lot of left-leaning people find crypto distasteful because it's so tied up with currencies and finance and trading and property rights and markets. So, just to start out, here's a list of various ideas/projects from within the crypto world that strike me as having appeal for people with left-wing personalities/perspectives.


## Environment

There are some really neat projects aimed at creating financial infrastructure that can promote environmental causes.

For example, MakerDAO (one of the early "stablecoin" projects, which created a token called Dai whose value is kept approximately-equal to 1 USD through clever decentralized mechanisms) has recently been floating an idea of becoming ["clean money"](https://forum.makerdao.com/t/the-case-for-clean-money/10684): requiring that the assets used as collateral to back Dai be "sustainable and climate-aligned assets". (i.e. If a shop wants to support environmental causes, it can require - or offer discounts for - payments in Dai rather than in some other currency.) I haven't been following them closely, but [here](https://medium.com/bankless-dao/makerdao-to-fund-sustainability-initiatives-6b8b4829237d) is another article that makes it sound as if they're still continuing down this path.

There's also a project called [KlimaDAO](https://www.klimadao.finance/) aimed at sucking up the supply of carbon offsets, to increase their price (the point being to both incentivize companies to reduce emissions rather than purchase offsets, and also to increase the reward for projects like planting trees and stuff like that). I don't know a lot about this project, but I think it's a neat example of people trying economically-interesting approaches to dealing with problems like climate change. (Minor note: please don't assume from the absurd-looking "7952% APY" that this is a ridiculously-obvious scam. KlimaDAO, and the OlympusDAO project that it's forked from, uses an interesting staking mechanism to incentivize people to hold their tokens rather than just sell them. The huge APY number is technically correct, but very confusing if you've never seen this before.)

Also, I just came across a link to [Regen Network](https://www.regen.network), which I know absolutely nothing about but it looks like this sort of thing too (economically-interesting blockchain-based approach to environmental issues).

Also, just to address the obvious environmental objection to crypto: Ethereum is switching over (within the next few months) to Proof-of-Stake as its consensus mechanism, and AFAICT most new blockchains are starting with PoS right from the outset. Like, one of the (valid!) arguments against Proof-of-Work chains (the main one being Bitcoin) is the massive wasted energy usage and computational capacity, but that was more a matter of "PoW was the first idea we had, but now we've got a better one." (Um, for Ethereum, anyway; don't ask me what's going on with the Bitcoin community.)


## Privacy

Again, just to get the obvious objection out of the way: of course early blockchains like Bitcoin and Ethereum are much *worse* in terms of privacy - *every* transaction is publicly visible.

But there are lots of privacy chains working on using zero-knowledge proofs and other clever cryptography to create chains/layer2s that are both trustworthy and private. (That is, projects to allow transactions that governments and big corporations can't track.) A few that I'm aware of: [Monero](https://www.getmonero.org/), [Zcash](https://z.cash/), [Tornado Cash](https://tornado.cash/), [Aztec](https://aztec.network/). There are probably a bunch of others.

I'm also vaguely aware of something called [Orchid](https://www.orchid.com/whitepaper/english.pdf), which IIUC is aiming to be like Tor but economically-scalable-and-sustainable. That is, it financially-incentivizes people to participate in making the network work, so that it can be sustainable at large scale (rather than relying on the much-smaller number of people who are willing to run onion-routing nodes out of altruism).

(That kind of incentivization is a common theme with this stuff: e.g. Filecoin versus IPFS. Whatever kind of decentralized-network-thingy we're talking about, you can probably get a small number of enthusiasts to run nodes, but if you want to get more participation than that, you need to make it worthwhile for the participants.)


## Public-goods funding

In general, funding [public goods](https://en.wikipedia.org/wiki/Public_good_(economics)) (which I mean in the technical economic sense of the word: goods that are non-rivalrous and non-excludable) is something markets do very badly (and governments aren't great at it, either). The crypto world has a whole bunch of ideas about ways that blockchains might do a better job of it.

One idea that's been seeing some significant-and-growing experimentation is [quadratic funding](https://vitalik.ca/general/2019/12/07/quadratic.html). [Gitcoin](https://gitcoin.co), which in general is an organization/DAO aimed at developing public goods in general and open-web-related public goods in particular, has an ongoing quadratic-funding system called Gitcoin Grants (2021 summary [here](https://gitcoin.co/blog/gitcoin-2021-year-in-review/)). It's like a donation-matching system, but instead of being linear (i.e. "each time you donate $1 to a project, the project also receives $N from the subsidy pool"), the matching formula gives a bigger subsidy to projects that receive lots of little donations than projects that receive a small number of big donations (e.g. a project that gets 100 $1 donations gets a lot more extra money from the subsidy pool than a project that gets 2 $50 donations). The point is that this is a decentralized way of *identifying* public goods: we want to subsidize the projects that many people value. (There's a clever mathematical argument for why quadratic is optimal in terms of incentivizing the behaviour we want.)

An Ethereum rollup called Optimism is also experimenting with an idea called ["retroactive public goods funding"](https://optimismpbc.medium.com/retroactive-public-goods-funding-33c9b7d00f0c). That's a newer experiment (I think they're only on round 1; results are [here](https://vitalik.ca/general/2021/11/16/retro1.html)), but I like that idea too. The idea is to try to spin up a whole venture-capital ecosystem for funding public goods. (Startup companies can get early funding because there's the hope of an "exit" at the end where the early investors can sell their shares because they're actually worth something; public-good projects don't have that, because the project doesn't make any money even if it turns out to be extremely valuable for the public. But maybe if there's a reliable source of retroactive funding, that can change, which will make it much easier for public-good projects to get the seed funding they need to get started in the first place.)


## Universal Basic Income

[democracy.earth](https://democracy.earth) has an interesting experiment with UBI infrastructure. It's not exactly aimed at solving the "where do we get the money to fund it?" problem (which is still the main obstacle, of course), but they've got a neat approach to building the infrastructure, which just kinda bypasses the mainstream political system entirely (which I do think is important, because holy shit how do you get anything at all accomplished in our train-wreck of a political system).

The basic idea is: "every human gets 1 UBI token per hour; now it's up to altruists to make those tokens actually worth something." That is, anyone who wants to fund UBI can simply buy these UBI tokens on the open market (e.g. "I'll buy up to N UBI tokens at $X each") using all the usual DeFi systems, and then burn them (because the point isn't to resell them, it's to altruistically fund the UBI system).

They've even got a Yearn Vault that lets people invest their money and have some portion of the *interest* used to buy-and-burn these UBI tokens. (i.e. It's an endowment, which is an idea familiar from the mainstream financial world.)

Again, obviously this doesn't solve the main problem of "who's going to fund it?". But I like the insight that we can decouple the two pieces of the problem by introducing an extra layer of indirection (i.e. a token); we've got the "give every human a steady income of this many tokens per year" already implemented, so now the story we can tell to rich philanthropists is, "The infrastructure is already in place; all you need to do to contribute to UBI is put money into this endowment fund." (And because that's so simple and straightforward, it may be a Schelling Point that we can get lots of support for.)


## Replacing legacy stuff with decentralized alternatives

Distrust of mainstream institutions is pretty much everywhere within crypto: dislike for both large corporations and governments, and belief that we're seeing the decline of Western civilization in general. (Not just our banking system, although that's been the first target for replacement, with cryptocurrencies and decentralized-finance, since it underpins everything else.)

So a big category of crypto applications are, "Replacing existing institutions with alternatives that are decentralized and censorship-resistant and open and don't require trusting big companies or governments," which I think are values that both right-wing and left-wing crypto people share.

Basically all of DeFi is aiming at disrupting and replacing our corrupt monetary system and banking system. (If you're the kind of leftist who wants a moneyless society, then maybe this strikes you as not going far enough. Personally, what I'd say is more like, "The core concepts of money and trade are good, but our current fiat-currency system and banking system are corrupt and much too closely in-bed with governments and regulators; they can't be trusted with that much power." I want financial infrastructure whose source code I can see, and that I can trust to run as-programmed.)


# Wrapping up

I've got more, but maybe that's enough for now.

The point here is that I think a lot of left-leaning people dismiss crypto because it's so tied up with currencies and finance and trading and property-rights and free-markets. So I think it's neat to see that there are a bunch of people in the crypto world who are making *use* of these new mechanisms in order to further causes that lefties care about.

I'll write another post about the more general ideas. But for now, I just wanted to try to convey the flavour of a lot of stuff that's going on in the crypto space. It's not just about finance; blockchains have a lot of potential for solving problems that lefties care about, and maybe for reducing some of the hatred/polarization between left and right.
