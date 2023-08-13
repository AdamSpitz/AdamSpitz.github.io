---
layout: page
title: Crypto FAQ For Normal People
---
# Crypto FAQ For Normal People

This FAQ is meant for people who have vaguely heard of crypto, or have maybe heard a bunch of (probably mostly negative) stuff about it in the news, but don't really know much about it.


"Wait, I thought crypto was dead."

Nah.


"But isn't crypto just a bunch of scams?"

It's like investing in dot-coms back in the 1990s. Tons of bad ideas, but the few good ones changed the world. (For more detail, see my page on [Crypto Scandals, Scams, Hacks, and Just Plain Dumb Ideas](/pages/crypto-scandals/).)


"Okay, what exactly is the point of crypto?"

The point of crypto is that we can build stuff where *you can see how something works just by looking at it*, rather than needing to trust any particular company or government or whatever.

(That's an oversimplification; bear with me.)

Trustworthy institutions are in short supply these days; it would be *really really nice* if we had a way to build *transparent* infrastructure.

(Also, with AI coming, this might be hugely important; AI is about to plunge us into a world where we have no idea what we can trust, and crypto's primary purpose is to let us make verifiable things.)


"I don't read code. How does it help me to have the thing's code be open and readable?"

The point isn't that you, personally, are going to read the code; the point is that *computer nerds who are unaffiliated with the computer nerds who wrote the code* can read the code (to determine whether the code does what its authors say it's supposed to do).

These people are called auditors; projects in the crypto world aren't considered trustworthy if they haven't been audited. (Bugs still slip through, and that's very bad. But still, auditing is a real thing that does actually happen as a routine standard practice.)


"So this is about Open Source software?"

Yes, but not *just* that.

If Google or Facebook or Twitter told you, "Here, we're open-sourcing the code that we run on our servers," you could go and read the code that they published, but you'd still have no guarantee that the code that they *say* they're running is the code that they're *actually* running. The whole point of a blockchain is that it adds *that* guarantee.

Imagine that Twitter not only said "here's the code that's running on our servers," but also *made their servers publish proofs* saying "here are all of the user-actions that our servers processed in the past few minutes, and here's the new current state of our database," and we could all run a verifier that quickly checks those proofs to make sure that what they did really is the correct result of running the code that they claimed to be running.

(That isn't just an analogy; that's exactly what would happen if Twitter ever decided to become a layer2 on top of a layer1 like Ethereum. Twitter would be publishing validity proofs, and you could run an Ethereum node that verifies those proofs. See my [Crypto Tech FAQ](/pages/crypto-tech/) for a bit more detail about the idea of L2s and validity proofs.)


"I still don't really see the point. I mean, I don't exactly *love* the Fed or banks or Twitter or video-game companies or whoever, but I don't think that the problem with them is that they don't do what they say they're going to do. I dislike those organizations for different reasons."

Yes, exactly! Sometimes the main reason why we *like* having some aspect of our society run by a large organization is because at least it's a big established thing with a name to protect and executives who don't want to go to jail, so even if it's kinda shitty for various other reasons, at least it's trustworthy in the most basic sense that it's not going to just outright abscond with our money.

So if we want to replace those kinds of organizations (because they're shitty in whatever way), it'd be nice to have some alternative way of making things that can be trusted in that most basic way.


"Okay, but I've been hearing about crypto for years now and nothing much has come of it."

The tech's not done yet.

See my [Crypto Tech FAQ](/pages/crypto-tech/) for more detail, but the bottom line is: cut the devs some slack. Building this stuff isn't easy. There's all sorts of progress being made all the time in many areas; it just takes time. At this point the endgame is in sight, though.

In particular, here are a few (solvable but not easy) technical problems that currently block mainstream adoption:
  - Scalability: Transactions cost dollars; many more apps become viable when transactions cost less than a penny.
  - Privacy: The point of blockchains is that we can write apps where all the activity can be verified (by anyone) as following the rules, but we also want privacy so that we can make apps where your transactions aren't just visible (to anyone). This sounds like a contradiction, but is doable with clever cryptography.
  - Wallets Are Terrifying: "Keep this 24-word account-recovery phrase secret and safe; you must never ever ever lose it or let anyone else see it, or you will lose all your money and there will be nothing that anyone can do about it."

We're not stumped on what to do about any of these; they all have solutions that are quite close to being ready. But it's taken years to get to this point.

If you roll your eyes when you hear me say "it'll be ready soon", fair enough; let's just wait and see.


"I heard crypto is bad for the environment."

That's no longer the case, except for Bitcoin.

The bad-for-the-environment thing is called "proof of work"; it was the first idea we had, and Bitcoin is still using it; nobody else who matters is still using it. In particular, Ethereum (the second-largest blockchain, and the largest general-purpose one) has already fixed this by moving to a better idea called "proof of stake". The environmental angle is a complete nonissue unless you're using Bitcoin specifically.


"So you're an Ethereum guy?"

Yeah.

You really don't want to get sucked into blockchain tribalism if you don't have to. As a layman, the only really important thing to understand is that blockchains are a general-purpose application platform; they're not just about money.

See my [Ethereum versus Other Blockchains](/pages/ethereum-versus/) page for more detail.


"Are you saying that I should buy ETH?"

No, I am really really not giving you financial advice. The technology has huge potential, but I have no idea whether the price of ETH (or anything else) will go up or down.


"Isn't this all just people hoping to get rich quick?"

AAA regulation?





There's all sorts of genuinely cool stuff happening in the crypto world; lots of progress on the technical front, lots of people building crypto versions of ordinary things as well as more-iden




"So if I'm used to developing ordinary web apps, I run it on an L2 instead of running servers of my own?"

You can do that - there are general-purpose L2s that are open for anyone to use - but we'll probably also end up seeing lots of app-specific L2s (and even L3s) run by individual companies. e.g. If you're developing a new game or a social-media app or whatever, you may want to write your server-side using one of the various L2 SDKs so that it publishes proofs that your app is doing what you claim it does.

(It's a terrible idea to start a new L1 just for your app, because you have to spin up its security from scratch by getting people to participate in running nodes. But app-specific L2s are a perfectly reasonable idea, if you want to have dedicated servers that are just for your app while still being able to prove to everybody that your app does what you claim it does.)
