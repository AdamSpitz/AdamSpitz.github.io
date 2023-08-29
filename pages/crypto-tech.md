---
layout: page
title: Crypto Tech FAQ For Normal People
---
# Crypto Tech FAQ For Normal People

This page is meant for normal people who'd like to know a *little* bit about the technical concepts behind blockchains, for the purpose of getting an intuitive sense of what the heck this stuff is and why it's hard.

I'll probably add more here later (I really like talking about this), but for now the main thing I want to talk about is the answer to this question:

"I've been hearing about crypto for years now and nothing much has come of it."

The tech's not done yet.

In particular, here are some big things that are currently inadequate (but have solutions that are in the works):
  - Scalability (transactions are expensive because throughput is low)
  - Privacy (everything is public, which is great for some purposes but bad for others)
  - Human-Friendly Self-Custody (account-recovery phrases are terrifying)


## Scalability

"What do you mean, scalability?"

Right now, Ethereum can do about 16 transactions per second. This means that each transaction is fairly expensive (dollars, not cents), because transactions are basically auctioned off. So the apps that are willing to pay the most get them.

That's good enough for some applications (like some financial ones), but many more applications (social media, gaming, etc.) become viable once we can do thousands of transactions per second at a cost of less than a penny.


"Why is making a scalable blockchain hard? I mean, Google and Twitter and Facebook and all the other big companies are running these huge web applications with gigantic databases; do you blockchain people just not know how to do that?"

A blockchain has to run on a normal computer affordable to normal people.

The whole point of a blockchain is that you (yes, you personally) can download a piece of software, run it on a normal affordable computer like a laptop or a desktop, and that software will follow along with everything going on on the blockchain and make sure that it's all valid (following the rules), plus maybe you even want it to participate in running the chain.

That's why Ethereum intentionally limits its throughput to a manageable level. In particular, the main bottleneck right now is storage space. (e.g. If you want to run an Ethereum validator, the recommendation is to have a 2 TB SSD, which is on the high end of normal these days but still affordable. CPU and RAM don't need to be anything special.) Running a blockchain client requires a lot of storage space because you need to be able to follow along with all the new transactions that are happening and make sure that they're all valid, and for that you need to store the entire current state of the chain (which keeps getting bigger and bigger over time). We don't want it to get too big too fast, because then it wouldn't run on ordinary consumer hardware anymore.

(There are also plans in progress for making "stateless" clients possible, so that you won't even need a large storage in order to fully follow along with verifying the chain; that kind of node ought to run even on a phone or even a smaller device.)


"Okay, but you've still got lots and lots of people running nodes, right? So doesn't it add up to a whole lot of computing power and storage space?"

You don't get it. They're all duplicating each other's work. Each of them is individually verifying the entire chain; that's the whole point of this. Adding more nodes to a blockchain doesn't make it *bigger*, it makes it more *secure*. (And in particular, *you* running your own node means that *you* can trust that everything going on is following the rules.)


"Okay, so how *are* these things going to scale up to running huge numbers of transactions?"

The key insight is that we don't need the massively-decentralized network to run all the transactions or store all the data; we just need it to *verify* that all the transactions have been run honestly and that all the data is available.

The obvious way to verify that all the transactions have been run honestly is to run all the transactions yourself. The obvious way to verify that all the data is available is to download all the data yourself. That's the way blockchains have worked until now.

But it turns out that it's possible, through clever cryptography and mechanism design, to separate "doing it" from "verifying that it was done honestly", for both computation and data-availability:

  - Computation: We need to compute the result of running a huge number of transactions. But there's a type of cryptography called "zero-knowledge proofs" that enables an untrusted computer to run a huge computation in such a way that it produces not only the result of the computation, but also a cheaply-verifiable proof that that result really is the correct result of running that particular computation. So your node (running on your own little computer) doesn't need to actually run all the transactions; it just needs to verify the validity proofs.
  - Data availability: A block producer needs to store, and make available for download, a large amount of data. But (again, through clever cryptography) it can store that data in a way that's amenable to "data availability sampling", in which your little computer can do a little bit of random sampling to verify that all the data is available. (This doesn't work if you do it the naive way. If a malicious block producer provides *most* of a block but withholds a tiny piece of it, you might randomly sample a few spots, see that they're available, and miss the fact that the tiny piece is missing. But there's a type of cryptography called "erasure coding" that makes it possible to transform, say, 1 MB of data into 2 MB of data, *any* 1 MB of which is sufficient to reconstruct the original 1 MB of data. Which means that a malicious data provider would need to withhold at least 50% of the data in order to withhold anything at all. And that's something that you *can* reliably catch using a small amount of random sampling.) (There's more to it than this, but maybe that gives you the flavour of it.)

In practice, what this means is that we split the system into "layers": Ethereum is "layer 1", and then there are lots of "layer 2" blockchains that publish proofs and data to layer 1.

L1 focuses on being very decentralized, even though that necessitates being low-throughput and hence having expensive transactions; it's not a problem that an L1 transaction is expensive, because a single L1 transaction is used to verify a large number of L2 transactions. (If you're an app developer, you put your app on an L2, not on L1; you don't want your users to have to make L1 transactions directly.)

An L2 doesn't need to be that decentralized, because nobody needs to trust the L2 to do its job honestly, since L1 is verifying everything the L2 says. (It's still worthwhile for the L2 to be somewhat decentralized, but only for the sake of liveness, not for correctness. Even if there was only a single computer running the L2, an attacker would only be able to shut it down, not make it break the rules.)


## Privacy

The great thing about blockchains is that everything happening on them is public.

The terrible thing about blockchains is that everything happening on them is public.

That is, we want some things to be public, and some things to be private. You probably don't want everyone in the world to be able to see everything you do.

In the current mainstream world, we (sort of) get privacy by trusting some company with your data and hoping they don't show it to anybody else. Your bank or credit-card company can see all your purchases, but hopefully they don't show anybody else. Facebook can see your private messages, but hopefully they don't [show](https://www.forbes.com/sites/emilybaker-white/2022/08/08/facebook-abortion-teen-dms/) anybody else. This doesn't work *fantastically* well, but at least it's a way in which privacy *can* happen.

On a blockchain, on the other hand, we can't just entrust our data to the company running it, because there *isn't* any company running it; the blockchain is open for anyone to participate in and verify.

"So let's let encrypt the data." No, it's not that simple, because we still need everything on the chain to be verified to be following the rules. How do you verify that it's valid if you can't see it?

Until now, that has meant that blockchains just didn't have any notion of privacy; everything happening on-chain was publically visible. That's great for use cases where we don't want privacy anyway, but it means blockchains can't handle use cases that do require privacy... unless we do something clever.

The clever thing that we do is going to involve zero-knowledge proofs. Up above I mentioned that ZK is great for scalability, because we can use them to produce a cheaply-verifiable proof of the validity of an expensive computation; the other thing ZK is great for is privacy, because we can produce a proof that shows that a computation is valid *without* revealing all of the information that went into that computation.

There's a very cool project called [Aztec](https://aztec.network/) (there may be other such projects too, I dunno) that is working on an L2 that enables privacy. That is, on Aztec it'll be possible for developers to make apps where your data is *not* all visible, even though your transactions can still be verified as valid. (I believe that idea is that you'll run the private part of the transaction - i.e. the part that actually requires your private data - locally on your own computer, and then your computer will submit, to the network, the *result* of that local computation, as well as a ZK proof that that result is honest.)


## Wallets Are Terrifying

If you want to control your own crypto "wallet", the current story we tell people is: "Here is your 24-word account-recovery phrase. You must never ever lose this and never ever let anyone else see it, or you will lose all your money and there is absolutely nothing that anyone will be able to do about it."

This is *terrifying*. Normal humans will (very reasonably!) not go for this.

In the mainstream world, if you lose the password to your online banking account, you can walk into your bank and show them your government-issued ID and they'll verify that you really are the person you claim to be and then they can set you up with a new password. (If you lose access to your Google account, there are ways of trying to recover that too, although I hear it can be awful.) This is scary for different reasons, and part of the point of crypto is that we don't really want to trust our bank (or Google or Twitter or whoever) with the master key that allows them the ability to recover or freeze or control our account. But still, "go talk to them and show your ID" is a much less terrifying user experience than the crypto 24-word-recovery-phrase thing.

There are various projects (e.g. [Argent](https://www.argent.xyz/) and [Soul Wallet](https://www.soulwallet.io/), but lots of others too) working on friendlier solutions to this. The main idea is "social recovery": instead of having a recovery phrase, you set up your wallet with some number of "guardians" (could be friends or family members, could be various pieces of hardware you own, whatever), and then if you need to recover access to your account, you need to get some number of your guardians to approve the recovery.

(The point is that this all works without any centralized company, including Argent or Soul Wallet or whoever, having any control at all over your account. They wrote the code, but now that code lives on-chain; if you want to, you can look at that code to make sure that they don't have any back doors into it.)

Lots of tweaking will be necessary before this is a viable solution for *everybody*, but it's certainly a step in a more human-friendly direction.
