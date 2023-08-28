---
layout: page
title: Blockchain Tribalism FAQ
---
# Blockchain Tribalism FAQ

"Ugh, there are [so many blockchains](https://www.coingecko.com/en/categories/layer-1). Do I really need to care about the differences between them?"

If you're reading this because you're considering putting some money into crypto or actually using some sort of blockchain-based application, then yes, for now you still need to care.

If you're reading this just because you're curious about what the heck the point is of all this crypto stuff, then there are a couple of high-level ideas that are worth understanding:

  - It's not just about currencies; it's a platform for apps. (This is why it's worthwhile to learn about more than just Bitcoin.)
  - It's hard to make a blockchain that can run gazillions of transactions per second while still being runnable by a normal person on affordable hardware. (This is the main reason why there are so many *other* blockchains competing with Ethereum.)


### It's not just about currencies

Crypto isn't just about money. Bitcoin was the first blockchain, and having a decentralized digital currency is a very cool and important application of blockchains, but now we have programmable blockchains upon which developers can create all sorts of applications. (It's like the difference between a calculator and a computer, or between an old dumb cell phone and a smartphone. Your computer has a calculator app on it, but it can do many other things too; your iPhone can make phone calls, but it can do many other things too.)

So if you're looking at a [list of blockchains](https://www.coingecko.com/en/categories/layer-1) and you think, "Ugh, I'd like to understand the point of this stuff, but I don't care about Blockchain X versus Blockchain Y; can't I just pick the first one on the list (Bitcoin) and learn about that one?"... no, if you want to understand what's going on, you need to at least look at the second one on the list (Ethereum) also, because Bitcoin is mostly just a currency, whereas Ethereum is a general-purpose application platform. There's a whole bunch of cool stuff being built in the crypto world, but almost none of it is happening on Bitcoin.

See my [Ethereum versus Bitcoin](/pages/ethereum-versus-bitcoin) page for more detail.


### Ethereum versus other general-purpose blockchains

"Okay, but if Ethereum is general-purpose, why are there so many other ones?"

There are major advantages to having everybody use the same blockchain, so new blockchains get started for roughly two reasons:
  1. They've got a cool new idea that is significantly better than what existing blockchains can do.
  2. Or it's a cash grab.

And of course projects of type #2 pretend that they're type #1. Also, people are pretty good at fooling themselves, so they might be sincere in thinking they're type #1.

Still, there are plenty of warts in the design of Ethereum; it's not like there aren't any ways to do better. The questions are more along the lines of: Is the improvement *enough* of an improvement to overcome Ethereum's massive already-existing ecosystem? Also, even if it's a big improvement, will Ethereum be able to simply adopt this improvement itself (or do something even better)? And are there any tradeoffs?


"What sorts of improvements are we talking about?"

The main technological goal of most of the current flock of Ethereum competitors is scalability. That is: "Hey, look, our blockchain can handle many many more transactions per second than Ethereum can."

Ethereum's answer to most of those is: "Yes, of course you can, but your approach to doing so sacrifices too much security/decentralization, which is the entire point of being a blockchain in the first place; if you want to be both scalable and secure/decentralized, you have to do something more like what we're doing." (See my [Crypto Tech FAQ](/pages/crypto-tech/) for more detail on what Ethereum is doing.)

And then the Ethereum-competitors say, "Nah, we're decentralized enough."

My own opinion is that Ethereum's approach is much more sensible; I've been very impressed by how well the Ethereum ecosystem has managed to stick to its principles and build things properly, rather than taking unsafe shortcuts. But justifying that opinion would require a much more technical discussion. Also, it's not like I actually understand everything that's going on here; I've tried to follow the main ideas of the technical innovations of some of the other blockchains, but there are a lot of them and it's hard. So you shouldn't actually trust anything I say here.


"What are these advantages to everybody using the same blockchain? Can't we just have a whole bunch of different ones, and maybe they can talk to each other or something?"

Yes, "bridges" are a thing. The problem is:
  - Bridges between layer1 chains are notoriously insecure. If you're bridging between blockchain A and blockchain B, your level of security is that of the *least secure* entity involved (i.e. blockchain A's security, blockchain B's security, and the bridge's security... whichever of those three is the worst, which is probably the bridge).
  - Also, we get better security overall if we have one blockchain with N validators, rather than 100 blockchains with N/100 validators each (because each of those small blockchains is much easier to attack, which will have ripple effects through the rest of the ecosystem).


"Why do the advocates of different blockchains hate each other so much?"

Crypto is a weird combination of idealism, economics, and technology.

That is:
  - People think (rightly) that blockchains have the potential to massively improve the world, so they can be very passionate about it.
  - The technology allows people to put their money where their mouth is, so they have a lot to lose if they're wrong and a lot to gain if they're right.
  - And a whole lot depends on technical details that are extremely hard to understand, so it's easy to argue and argue and argue and argue and argue without ever resolving anything.
