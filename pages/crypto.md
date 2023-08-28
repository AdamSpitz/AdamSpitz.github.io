---
layout: page
title: Crypto FAQ For Normal People
---
# Crypto FAQ For Normal People

This FAQ is meant for people who don't really know much about crypto, but are mildly curious about it. Maybe you've heard a bunch of (probably mostly negative) stuff about it in the news, or maybe you're sympathetic.


"Isn't crypto just a bunch of scams?"

It's like investing in dot-coms back in the 1990s. Tons of bad ideas, but the few good ones changed the world. (For more detail, see my page on [Crypto Scandals, Scams, Hacks, and Just Plain Dumb Ideas](/pages/crypto-scandals/).)


"Okay, what exactly is the point of crypto?"

The point of crypto (and please bear with me while I oversimplify) is that we can build stuff where *you can see how something works just by looking at it*, rather than needing to trust any particular company or government or whatever.

Trustworthy institutions are in short supply these days; it would be *really really nice* if we had a way to build *transparent* infrastructure.

The question of which *particular* crypto use-case (finance, social media, gaming, science, identity, public-goods, etc.) will give you that "a-ha" moment depends on what stuff you care about and what your political leanings are and what your interests are and so on. But I rarely encounter anyone who doesn't feel like at least *some* of the big powerful organizations (corporations or government institutions or whatever) that run our world are kinda shitty and wow yeah it'd really be kinda nice if we could replace them with some code that does what they're *supposed* to do but in a transparent and trustworthy way.

(Also, with AI coming, this might be hugely important; AI is about to plunge us into a world where we have no idea what we can trust, and crypto's primary purpose is to let us make verifiable things.)


"I don't read code. How does it help me to have the thing's code be open and readable?"

The point isn't that you, personally, are going to read the code; the point is that *computer nerds who are unaffiliated with the computer nerds who wrote the code* can read the code (to determine whether the code does what its authors say it's supposed to do).

There are no restrictions on who's allowed to do this, but there are professional people who do it, called auditors; projects in the crypto world aren't considered trustworthy if they haven't been audited. (Bugs still slip through, and that's very bad. But still, auditing is a real thing that does actually happen as a routine standard practice.)


"So this is about Open Source software?"

Yes, but not *just* that.

If Google or Facebook or Twitter told you, "Here, we're open-sourcing the code that we run on our servers," you could go and read the code that they published, but you'd still have no guarantee that the code that they *say* they're running is the code that they're *actually* running. The whole point of a blockchain is that it adds *that* guarantee.

Imagine that Twitter not only said "here's the code that's running on our servers," but also *made their servers publish proofs* saying "here are all of the user-actions that our servers processed in the past few minutes, and here's the new current state of our database," and we could all run a verifier that quickly checks those proofs to make sure that what they did really is the correct result of running the code that they claimed to be running.

(That isn't just an analogy; that's exactly what would happen if Twitter ever decided to become a layer2 on top of a layer1 like Ethereum. Twitter would be publishing validity proofs, and you could run an Ethereum node that verifies those proofs. See my [Crypto Tech FAQ](/pages/crypto-tech/) for a bit more detail about the idea of L2s and validity proofs.)


"I still don't really see the point. I mean, I don't exactly *love* the Fed or banks or Twitter or video-game companies or whoever, but I don't think that the problem with them is that they don't do what they say they're going to do. I dislike those organizations for different reasons."

Yes, exactly! Sometimes the main reason why we *like* having some aspect of our society run by a large organization is because at least it's a big established thing with a name to protect and executives who don't want to go to jail, so even if it's kinda shitty for various other reasons, at least it's trustworthy in the most basic sense that it's not going to just outright abscond with our money.

So if we want to replace those kinds of organizations (because they're shitty in whatever way), it'd be nice to have some alternative way of making things that can be trusted in that most basic way. That is, crypto opens up possibilities for little guys to be just as trustworthy as big guys; you don't *need* to be a huge stodgy organization in order for the code you write to be trustworthy, because people can just read it and make sure it does what you say it does.


"Okay, but I've been hearing about crypto for years now and nothing much has come of it."

The tech's not done yet.

See my [Crypto Tech FAQ](/pages/crypto-tech/) for more detail, but the bottom line is: cut the devs some slack. Building this stuff isn't easy. There's all sorts of progress being made all the time in many areas; it just takes time. At this point the endgame is in sight, though.

In particular, here are a few (solvable but not easy) technical problems that currently block mainstream adoption:
  - Scalability: Transactions cost dollars; many more apps become viable when transactions cost less than a penny.
  - Privacy: The point of blockchains is that we can write apps where all the activity can be verified (by anyone) as following the rules, but we also want privacy so that we can make apps where your transactions aren't just visible (to anyone). This sounds like a contradiction, but is doable with clever cryptography.
  - Wallets Are Terrifying: "Keep this 24-word account-recovery phrase secret and safe; you must never ever ever lose it or let anyone else see it, or you will lose all your money and there will be nothing that anyone can do about it."

We're not stumped on what to do about any of these; they all have solutions that are quite close to being ready. But it's taken years to get to this point.

If you roll your eyes when you hear me say "it'll be ready soon", that's a totally fair response from an outsider's point of view. I've been following along closely enough that I can see all sorts of awesome technological development going on; it's very obvious that they're not just stuck. They're making tons of progress, and the roadmap is quite clear at this point.


"Isn't crypto all just people hoping to get rich quick?"

Not *all*. But yes, there's a ton of that.

I have three things to say about that:
  - If your objection is "it's immoral to get rich by being an early investor": no, there's nothing wrong with seeing the potential in these technologies and putting your money where your mouth is.
  - If your objection is "naive people are going to *try* to get rich quick but end up losing their money; they're basically just gambling": It *is* sad, but I also don't think paternalistic regulation is a good answer, because there really is a lot of amazing potential here (which many investors actually understand a lot *better* than the regulators and politicians) and it's shitty for regulators who don't understand that to be blocking people who do from taking advantage of this opportunity.
  - If your objection is "I find it distasteful to hang around with people with such crass motivations": there are a *ton* of genuinely wholesome optimistic builders/believers in the crypto space, people who care a lot more about the technology or the societal benefits rather than the asset prices. That's a big part of what I love about it.


"I heard crypto is bad for the environment."

That's no longer the case, except for Bitcoin.

The bad-for-the-environment thing is called "proof of work"; it was the first idea we had, and Bitcoin is still using it; nobody else who matters is still using it. In particular, Ethereum (the second-largest blockchain, and the largest general-purpose one) has already fixed this by moving to a better idea called "proof of stake". The environmental angle is a complete nonissue unless you're using Bitcoin specifically.


"So you're an Ethereum guy?"

Basically, yeah.

You can go read my [Blockchain Tribalism FAQ](/pages/blockchain-tribalism/) if you want to, but I recommend against it; as a layman, you probably don't want to get sucked into blockchain tribalism. The only really important thing to understand, for the purpose of getting a high-level overview of the space, is that blockchains are a general-purpose application platform; they're not just about money (which means that if you only learn about Bitcoin, you'll get a very limited picture of what this is about).


"Are you saying that I should buy ETH?"

No, I am really really not giving you financial advice. The technology has huge potential, but I have no idea whether the price of ETH (or anything else) will go up or down.
