---
layout: page
title: Proof Of Work versus Proof Of Stake
---
# Proof Of Work versus Proof Of Stake

For all practical purposes, this is a sub-argument within the [Bitcoin versus Ethereum](/pages/ethereum-versus-bitcoin) argument. Except for Bitcoin, no blockchain that matters uses proof-of-work. And now that Ethereum has switched from proof-of-work to proof-of-stake (in September 2022 - google "The Merge"), it's a big difference between Ethereum and Bitcoin. And those are the two biggest ones, so Bitcoiners who want to snipe at other blockchains generally focus their attention on Ethereum.


"Why does this nerdy technical-sounding thing even matter?"

Proof-of-work is the thingy where the people participating in running Bitcoin expend huge amounts of electricity and hardware.

This is:
  - very expensive;
  - and a [significant](https://digiconomist.net/bitcoin-energy-consumption) component of the world's electricity consumption (though you may or may not care about that from an environmental perspective; I'm not taking a position on it here, I just think it's obviously worth mentioning because many people *do* care about it).

The Bitcoiners' counterargument is that the alternative thingy, "proof of stake", is insecure or something. Honestly, I don't think their arguments make much sense; I'll go into them a bit later on this page. But you should at least know that that's what the argument is about.

And Ethereum's counter-counterargument is that the security of proof-of-stake isn't just not-worse, it's actually better. I'll go into that more later too.


"What do you mean by 'expensive'?"

A blockchain (like Bitcoin or Ethereum) needs to pay the people who run it. This payment comes from two sources: the users using the blockchain, and the holders of the blockchain's native token (BTC or ETH).

Tha tis:
  - To some extent the block producers are paid by transaction fees (i.e. the people *using* the blockchain pay the people *running* the blockchain).
  - And to some extent they're paid by newly-minted tokens (BTC or ETH). The rules of the protocol say that whoever produces the next block is allowed to make up some new BTC or ETH out of thin air (the amount is called the "block reward") and claim it as their own.

So both BTC and ETH undergo some amount of inflation (although the story is more complicated than that; I'll go into it more below). In that sense, the people *holding* BTC and ETH are paying the block producers for running the blockchain (by having the value of their BTC or ETH diluted, since minting new tokens means there are more of them in existence).

The question is: how *high* do the block rewards need to be?

And the point is that a proof-of-work chain (i.e. Bitcoin) needs to pay its block producers quite a lot just to compensate them for the expense of expending all of that electricity and hardware. (The hardware needs to be replaced every couple of years.)

In contrast, a proof-of-stake chain requires its block producers to lock up a bunch of money as their "stake" (like a security deposit - the idea is that if they're incompetent or malicious, they'll lose part of all of their stake), so they need to be compensated for the opportunity cost of locking up that money. But that's a much lower amount than the amount needed to compensate proof-of-work miners for the expended electricity and hardware.

So proof-of-work chains are much more expensive to run, in the sense that they need much higher levels of new issuance.

To illustrate (though this isn't a Bitcoin-vs-Ethereum comparison, this is an old-Ethereum-vs-new-Ethereum comparison): back when Ethereum was using proof-of-work, new ETH issuance was something like 4.5% per year. (That is, the amount of newly-minted ETH every year was something like 4.5% of the total amount of ETH in existence.) When Ethereum switched from proof-of-work to proof-of-stake, that went down to something like 0.5% per year. I should probably go look up those numbers to make sure I've got them right, but seriously, it's a *lot* less.


"So BTC and ETH are both inflating, but BTC is inflating more?"

Here's where the stories get a bit more complicated.

Bitcoin's story is: they cut the block reward in half every four years. So the supply of BTC isn't actually going to inflate forever; it'll eventually asymptotically approach 21 million BTC, and won't ever be any more than that. (Unless they change the rules, which I suspect they'll have to do if they don't want to drop too many of their block producers.)

Ethereum's story is: not only is new-ETH-issuance very low, we also have a *deflationary* mechanism - a portion of every transaction fee is "burned" (destroyed) as a sort of congestion tax. Ever since Ethereum ditched proof-of-work, the amount of ETH minted as block rewards has actually been [less](https://ultrasound.money/) than the amount of ETH burned via the congestion tax. This means that ETH is slightly-deflationary overall.

I think I'll leave the argument over the merits of this on my [Ethereum versus Bitcoin](/pages/ethereum-versus-bitcoin) page. I only mentioned this here because I wanted to explain the basic idea that the costs of proof-of-work are paid for via inflation.


"Okay, so proof-of-work is expensive. What do the Bitcoiners claim the advantage is, then?"

As far as I can tell (and here I'd actually love to hear from a Bitcoiner who can explain this coherently), their arguments are something like:

  - "There's nothing backing up the value of your coin! It's just a Ponzi. Whereas Bitcoin is backed by real electricity." This is just nonsense; the Bitcoiners who say this are doing the accounting wrong. The electricity spent mining Bitcoin is a cost, not an asset. It isn't stored within the coin like a battery; it's an expense that the Bitcoin miners need to be compensated for. (It's true, though, that with both BTC and ETH, if their price goes down, their level of security will go down. Proof-of-work doesn't fix this, it just adds an extra complication to the story. If the price of BTC decreases, the value of the mining rewards goes down, so the amount of mining will go down.)
  - "Proof-of-stake means that the rich get richer." Yes. Proof-of-work is like that too, only more so (because of economies of scale - mining equipment and electricity are cheaper the more of them you buy). At least with proof-of-stake it's a linear relationship: if you stake 10x as much, you get 10x the reward, not more than that.
  - "Ethereum is run by centralized staking pools that can be controlled by the government." Um, no. Proof-of-work mining operations have huge resource requirements that make them easily trackable. Whereas proof-of-stake validators are tiny and cheap and easy to move; also, the staked ETH can simply be withdrawn and moved to a different validator. Also blah blah Lido Rocketpool etc. Ugh, I'm really tired of this.
  - "Governments are going to declare ETH to be a security (making it subject to various onerous laws), whereas BTC is obviously a commodity." This seems unlikely, though ETH's legal status in the US isn't completely resolved yet, and I'm not saying I have a huge amount of faith in US regulators/legislators to do the right thing.


"You mentioned earlier that proof-of-stake's security is actually *better*?"

The big thing is that a malicious staker will *lose* his stake.

If someone *does* manage to execute a 51% attack on Bitcoin (which is unlikely, because it'd require a *lot* of computing power), Bitcoin can't really punish them. (They can change the proof-of-work algorithm to make *all* the ASICs useless, but (a) that only works once, and (b) it punishes the honest 49% of miners too.) The attacker can simply keep on doing this.

Whereas if someone manages to execute a 51% attack on Ethereum (which is also unlikely, because it'd require a *lot* of ETH), the attacker will take down Ethereum for a short time and then lose all their staked ETH (many billions of dollars' worth). Not really the kind of thing an attacker can afford to keep doing over and over.
