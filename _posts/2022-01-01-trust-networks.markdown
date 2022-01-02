---
layout: post
title:  "Subjective, trust-network-based tagging and voting/rating"
date:   2022-01-01
---
I don't think permissionless shared-spaces (like subreddits, or like all-of-Twitter - that is, shared spaces that may have moderation systems for kicking people out, but that are open by default) are going to be viable in web3.

A general theme of crypto/blockchains/web3 is [mechanism design](https://en.wikipedia.org/wiki/Mechanism_design): creating systems that have good emergent behaviour when the individual players follow their own selfish incentives. We're learning more and more about how to create decentralized systems that can behave the way we want them to without being derailed by malicious actors. I think web3 social-media platforms will need to be more-explicitly designed along those lines: more attention paid to making sure that the system doesn't allow spammers or trolls or other bad actors to impose costs on others.

In web2, most activity happened on giant platforms owned by just a few companies (Facebook, Twitter, etc.). Having the company as a Central Controller causes a lot of problems (which is a big part of the appeal of web3 in the first place), but does have the advantage of having a clear entity who ultimately has the power and the motivation to police the platform, set the rules, moderate/ban/censor people they consider to be bad actors, etc.

In web3, we want to avoid having those kinds of huge centralized entities in control of our social-media systems. We want systems that are permissionless and trustless. Which means that we're going to need to design our systems to be more resistant to attackers, because they need to function well without a centralized policeman who can fix problems after they've happened.

In particular, one obvious potential problem is [Sybil attacks](https://en.wikipedia.org/wiki/Sybil_attack): e.g. an attacker might automatically create millions of accounts and spam a group with posts or upvotes/downvotes.

For social-media systems, I don't think our existing decentralized sybil-resistance mechanisms are appropriate:

  - Proof-of-Work and Proof-of-Stake require a large amount of money to gain influence, whereas we probably want social-media accounts to be cheap/free to create.
  - Unique-human identification systems like [Proof of Humanity](https://www.proofofhumanity.id/) and [BrightID](https://www.brightid.org/) also don't seem quite right; we probably don't want to limit social-media accounts to one per human, and we also probably don't want to have everyone's account associated with their real-world identity; allowing multiple accounts and pseudonyms is a feature, not a bug. (Maybe clever ZK-proof technology can help, though?)

The best solution I can see is for new accounts to have zero influence. Make the system require you to convince others to opt-in to hearing what you think, rather than requiring them to opt-out. If you want people to take your posts/votes into account, you'll need to convince them to follow you, get the group to add you as a member, etc. Let people create a million accounts if they want; there won't be anything stopping them from doing it, but it won't benefit them, because a fresh account will have no power.

I think this means that we'll end up with trust networks playing a bigger role in web3 social media than they did in web2. You'll have a list of people whose judgment you trust, and maybe that trust will be transitive to some extent (i.e. you trust whoever the people you trust trust) (but with the ability to override their judgment).

e.g. I'm imagining a general-purpose upvoting/downvoting system, like Reddit, except that your personal UI only shows you the tally of votes by people who are (transitively) included within your trust network. Spammers and trolls and people-on-the-opposite-side-of-the-political-aisle-from-you can create as many accounts as they want and upvote as many dumb posts as they want, and your UI will never see them. (Which obviously has the potential to make our echo-chamber problem even worse than it already is, but... well, see the [reducing polarization](https://www.reddit.com/r/Web3SocialMedia/comments/rreil8/thoughts_on_reducing_political_polarization/) post.)

One wrinkle is that trust is domain-specific. (e.g. I have friends whose judgment I trust when it comes to programming languages, but not when it comes to politics or music.) So maybe we'll need some sort of tagging system to tag content items, and then we can have different trust-networks for different tags ("here's who I trust on music", "here's who I trust on politics", etc.).

(And then of course we'll need the tagging system to also be Sybil-resistant. So I think tagging will need to be done in this kind of subjective trust-network-based way, too.)

(Crossposted [on /r/Web3SocialMedia](https://www.reddit.com/r/Web3SocialMedia/comments/rttazk/subjective_trustnetworkbased_tagging_and/); feel free to comment there.)
