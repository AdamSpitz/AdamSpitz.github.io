---
layout: page
title: Crypto Tech FAQ For Normal People
---
# Crypto Tech FAQ For Normal People

"I've been hearing about crypto for years now and nothing much has come of it."

The tech's not done yet.

In particular, here are some big things that are currently inadequate (but have solutions that are in the works):
  - Scalability (transactions are expensive)
  - Privacy (everything is public)
  - Human-Friendly Self-Custody (account-recovery phrases are terrifying)


## Scalability

"What do you mean, scalability?"

Right now, Ethereum can do about 12 transactions per second, and each transaction costs dollars (because transactions are basically auctioned off, so the apps that are willing to pay the most get them).

That's good enough for some applications (like some financial ones), but many new applications (social media, gaming, etc.) become viable once we can do thousands or millions of transaction per second at a cost of less than a penny.


"Why is making a scalable blockchain hard? I mean, Google and Twitter and Facebook and all the other big companies are running these huge web applications with gigantic databases; do you blockchain people just not know how to do that?"

A blockchain has to run on a normal computer affordable to normal people.

The whole point of a blockchain is that you (yes, you personally) can download a piece of software, run it on a normal affordable computer like a laptop or a desktop or a NUC or whatever, and that software will follow along with everything going on on the blockchain and make sure that everything happening is valid (following the rules), plus maybe you want it to participate in running the chain.

Ethereum intentionally limits its throughput to a manageable level. In particular, the main bottleneck is storage space. (e.g. If you want to run an Ethereum validator, the recommendation is to have a 2 TB SSD, which is on the high end of normal these days but still affordable. CPU and RAM don't need to be anything special.) Running a blockchain client requires a lot of storage space because you need to be able to follow along with all the new transactions that are happening and make sure that they're all valid, and for that you need to store the entire current state of the chain (which keeps getting bigger and bigger over time). We don't want it to get too big too fast, because then it wouldn't run on ordinary consumer hardware anymore.


"Okay, but you've still got lots and lots of people running nodes, right? So doesn't it add up to a whole lot of computing power and storage space?"

You don't get it. They're all duplicating each other's work. Each of them is individually verifying the entire chain; that's the whole point of this. Adding more nodes to a blockchain doesn't make it *bigger*, it makes it more *secure*.


"Okay, so how *are* these things going to scale up to running huge numbers of transactions?"

The key insight is that it turns out that it's possible, through clever cryptography and mechanism design, to separate "doing a huge amount of stuff" from "verifying that all that stuff is being done honestly."

I mean that in two different ways:
  - Computation: We need to compute the result of running a huge number of transactions. But we can use a type of cryptography called "zero-knowledge proofs" to enable a normal computer to quickly verify that a huge computation (done by some other, untrusted computer) was done honestly. So your node (running on your own little computer) doesn't need to actually run all the transactions; some other more-powerful computer out there can produce a block containing a whole lot of transactions, but do so in such a way that it produces a "validity proof" demonstrating that the answer it gave you really is the correct result of running that huge computation. Then all your computer needs to do is verify that that proof is valid (which it can do quickly and cheaply).
  - Storage: We need to store, and make available for download, a huge amount of data. But (again, through clever cryptography) we can store that data in a way that's amenable to "data availability sampling", in which your little computer can do a little bit of random sampling to verify that all the data is available. (This doesn't work if you do it the naive way. If a malicious block producer provides *most* of a block but withholds a tiny piece of it, you might randomly sample a few spots, see that they're available, and miss the fact that the tiny piece is missing. But it's possible to transform, say, 1 MB of data into 2 MB of data, *any* 1 MB of which is sufficient to reconstruct the original 1 MB of data. Which means that a malicious data provider would need to withhold at least 50% of the data in order to withhold anything at all. And that's something that you *can* reliably catch using a small amount of random sampling.) (There's more to it than this, but maybe that gives you the flavour of it.)

In practice, what this means is that we split the system into "layers": Ethereum is "layer 1", and then there are lots of "layer 2" blockchains that publish proofs and data to layer 1.

L1 is small but decentralized (i.e. runs on affordable hardware, so many people can run their own node); an L2 can run much larger numbers of transactions because it doesn't need to be nearly so decentralized, because it's publishing proofs to L1 so that L1 can verify that everything the L2 is doing is honest. (It'd almost be fine to just have the L2 running on a single supercomputer. We want more than that just for the sake of liveness - i.e. in case the single supercomputer goes down - but we don't need to worry about the L2's honesty, because no one's going to trust anything the L2 says until it's published to L1 and L1 has verified that it's valid.)


## Privacy

The great thing about blockchains is that everything happening on them is public.

The terrible thing about blockchains is that everything happening on them is public.

That is, we want some things to be public, and some things to be private. You probably don't want everyone in the world to be able to see everything you do.

In the current mainstream world, we (sort of) get privacy by trusting some company with your data and hoping they don't show it to anybody else. Your bank or credit-card company can see all your purchases, but hopefully they don't show anybody else. Facebook can see your private messages, but hopefully they don't [show](https://www.forbes.com/sites/emilybaker-white/2022/08/08/facebook-abortion-teen-dms/) anybody else. This doesn't work very well.

On a blockchain, there *isn't* any centralized organization running it. But we still need everything on the chain to be verified to be following the rules. Until now, that has meant that everything happening on-chain was publically visible. That's great for the things that we want to be publically visible, but it means there's no such thing as privacy on-chain... unless we do something clever.

The clever thing that we do is going to involve zero-knowledge proofs. Up above I mentioned that ZK is great for scalability, because we can use them to produce a cheaply-verifiable proof of the validity of an expensive computation; the other thing ZK is great for is privacy, because we can produce a proof that shows that a computation is valid *without* revealing all of the information that went into that computation.

There's a very cool project called [Aztec](https://aztec.network/) (there may be other such projects too, I dunno) that is working on an L2 that enables privacy. That is, on Aztec it'll be possible for developers to make apps where your data is *not* all visible, even though your transactions can still be verified as valid. (I believe that idea is that you'll run the private part of the transaction - i.e. the part that actually requires your private data - locally on your own computer, and then your computer will submit, to the network, the *result* of that local computation, as well as a ZK proof that that result is honest.)


## Wallets Are Terrifying

If you want to control your own crypto "wallet", the current story we tell people is: "Here is your 24-word account-recovery phrase. You must never ever lose this and never ever let anyone else see it, or you will lose all your money and there is absolutely nothing that anyone will be able to do about it."

This is *terrifying*. Normal humans will (very reasonably!) not go for this.

In the mainstream world, if you lose the password to your online banking account, you can walk into your bank and show them your government-issued ID and they'll verify that you really are the person you claim to be and then they can set you up with a new password. (If you lose access to your Google account, there are ways of trying to recover that too, although I hear it can be awful.) This is scary for different reasons, and part of the point of crypto is that we don't really want to trust our bank (or Google or Twitter or whoever) with the master key that allows them the ability to recover or freeze or control our account. But still, "go talk to them and show your ID" is a much less terrifying user experience than the crypto 24-word-recovery-phrase thing.

There are various projects (e.g. [Argent](https://www.argent.xyz/) and [Soul Wallet](https://www.soulwallet.io/)) working on friendlier solutions to this. The main idea is "social recovery": instead of having a recovery phrase, you set up your wallet with some number of "guardians" (could be friends or family members, could be various pieces of hardware you own, whatever), and then if you need to recover access to your account, you need to get some number of your guardians to approve the recovery.

(The point is that this all works without any centralized company, including Argent or Soul Wallet or whoever, having any control at all over your account. They wrote the code, but now that code lives on-chain; if you want to, you can look at that code to make sure that they don't have any back doors into it.)

I think lots of tweaking will be necessary before this is a viable solution for *everybody*, but it's certainly a step in a more human-friendly direction.
