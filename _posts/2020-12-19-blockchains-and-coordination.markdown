---
layout: post
title:  "Blockchains and coordination"
date:   2020-12-19
---
I'm getting excited about blockchains and smart contracts. In particular, I'm getting excited in a "holy crap, this might help humanity get its act together" kind of way, which is probably overly-enthusiastic, but on the other hand if you're too cynical you fail to notice the things that really are big and important, so I want to run with this feeling for a while.

I'm very new at all this crypto/blockchain stuff. I'm not an expert who understands the field; I'm a newcomer who's just starting to vaguely understand what all the fuss is about. So I think this might be a really good time to to try to write up what I'm learning, before I get so deep into it that I can't remember what it feels like to be a beginner looking at it from the outside. I think I know at least a few people who are in a similar position and who might also be interested.

When I say "get our act together", what I mean, more specifically, is "solve more types of coordination problems". But if I'm trying to articulate what's motivating me to care about this, it's more like "find realistic solutions to idealists' complaints", or "get the left and right to stop bickering over Markets versus Governments in situations that neither handles well", or "give us tools that will allow us to actually solve some problems that we all hate each other for not being able to solve", or something like that. Blockchains seem like they might offer some new solutions to old problems.

I'm idealistic enough that I would like to "do some good in the world", but I'm old enough to have noticed that the solutions proposed by idealists tend to blow up in everybody's face; the thing about the blockchain space that's caught my attention is that a lot of the people working in it have an interesting mix of hopeful idealism, pragmatic economic savvy, and technical ingenuity.

Some of the kinds of problems that seem like they might be more-solvable now:

  - How do we get a large number of people to jump from X to Y at the same time?
  - How do we fund public goods?
  - How do we *identify* public-good projects that are worth funding?
  - Can we create large organizations that don't suck so much?

## Coordination problems

Coordination problems are infuriating, because the [technical definition](https://www.oxfordreference.com/view/10.1093/oi/authority.20110803095637587) is something like, "a problem that would be so damned easy to solve if we could just work together". That's why we argue over them endlessly and blame each other (especially our political opponents) for failing to solve them.

That is, I'm not talking about problems that we just don't know how to solve, like "cure cancer" or "discover the ultimate laws of physics". Laypeople understand that those are hard problems, and that they don't know what the solution is.

With coordination problems, the difficulty isn't figuring out what to do, or even getting people to agree that we should do it. (I mean, of course it's impossible to get *everybody* to agree to anything. But most problems don't need *all* the people to be on board, just *enough* people.) I'm talking about the type of problem where we already know what we want to do, and enough people *can* play their parts, and enough people would be *willing* to play their parts (as long as enough other people play theirs)… and yet we *still* can't manage to coordinate to actually make it happen.

The usual pattern is: We're all doing X, but doing Y would obviously be better. But if only a few people switch to Y, they're penalized for it because everybody else is still doing X. So everyone sits around lamenting the fact that we're still stuck doing X instead of Y. How can we get a large group of people to switch from X to Y at the same time?

As a particular (but still very broad) subcategory: How can we fund [public goods](https://en.wikipedia.org/wiki/Public_good_(economics)) like open-source software, scientific research, scientific-experiment replications, public parks, environmental cleanup, etc.? (Lots of people want the project to be funded, and many of them would be willing to chip in their fair share as long as enough other people do.)

Not all of our problems fit that description. But many of them do. If we had a standard, reliable mechanism for solving those kinds of problems, we could fix *so many* things. If you want to get a sense of why this kind of problem is so important and so aggravating, I recommend [chapter 3 of Eliezer Yudkowsky's Inadequate Equilibria](https://equilibriabook.com/molochs-toolbox/) and Scott Alexander's [Meditations on Moloch](http://slatestarcodex.com/2014/07/30/meditations-on-moloch/).

We already have solutions (markets, governments, contracts…) that work well for *some* kinds of coordination problems, but not all kinds. Blockchains, and particularly smart-contract systems like Ethereum, bring an interesting combination of abilities to the table – a combination we haven't had before, which might enable us to solve problems that so far we haven't had good solutions for.


## Mainstream solutions to coordination problems

Before I talk about the cool new stuff, I think it's a good idea for me to risk offending all possible readers by describing how this situation relates to contemporary politics.

Markets and governments are both *coordination mechanisms* – that is, they enable large numbers of people to work together and accomplish tasks bigger than any of them could accomplish individually.

Neither of those mechanisms does a great job of everything, though. A lot of our politically-polarized strife consists of people fighting over whether to use markets or governments to handle situations that neither handles well. Right-leaning people point out that markets are really great for lots of things. Left-leaning people point out that there are also a bunch of things that markets don't handle very well, and that the best solution we've got for handling market failures is to have the government step in. The right points out that governments tend to be lousy at whatever they do. Those points are all correct, but if you believe them all simultaneously then you have to admit that the world is complicated and that you don't have a good solution, so most people prefer to polarize into two opposing camps and declare their undying hatred for each other.

(Though I also want to mention that not *all* of the markets-versus-governments conflict is like this; some of it is over situations in which one of the two actually *would* work very well, especially if it weren't being blocked by the ideologically-motivated stubbornness of the other side. In those kinds of situations, I am totally in agreement with you that your side is obviously right and the other side is obviously wrong.)

Economists actually have a pretty decent understanding of what kinds of problems markets are good at solving. Markets work particularly well for producing [private goods](https://en.wikipedia.org/wiki/Private_good) – goods that are [rivalrous](https://en.wikipedia.org/wiki/Rivalry_(economics)) (if I consume it, you can't consume it) and [excludable](https://en.wikipedia.org/wiki/Excludability) (if you haven't paid for it, we can prevent you from consuming it), like food or clothing or cars. The problem of producing private goods has the very nice property of being *compositional* – we can break up a large task into a bunch of small tasks, and let each individual person/business solve its own task using its own local knowledge and following its own incentives, and if the individual solutions are reasonably good then the overall solution will be reasonably good too. Fans of markets like to talk about how even an object as simple as [a pencil](https://fee.org/articles/i-pencil/) is the result of collaboration between millions of people, though none of them knows how to do more than a tiny fraction of the work. Coordination happens via price signals, despite the fact that no one person controls or even understands the entire system.

But markets don't work so well for goods that are non-rivalrous or (especially) non-excludable. (Markets also struggle when there are high transaction costs, asymmetric information, and [various other problems](https://en.wikipedia.org/wiki/Market_failure), but those aren't the ones I want to talk about right now.) For public goods – that is, goods that are non-rivalrous *and* non-excludable, like clean air, open-source software, scientific research, and so on – the structure of the individual incentives *doesn't* lead to the overall results we want. So we need a different kind of coordination mechanism.

Typically that's a government: we have people in charge who have the power to make laws and collect taxes and who are (in theory) supposed to use those powers to handle various things that markets don't handle well. The appeal of having a centralized coordinating agency for solving coordination problems is obvious: if we need coordination, let's put a coordinator in charge. That way we can just bypass the entire "the individual incentives don't lead to good results" problem.

Unfortunately, governments tend to suck at a lot of things. When markets work well, it's because there are competitive forces ensuring that competent businesses prosper and incompetent businesses fail. But there are only very weak competitive forces acting on governments, since they generally have a monopoly on whatever they're doing. (If you have a lousy experience at the DMV, you can't take your business to the competing DMV.)

Still, at least governments are held accountable by the voters, who are thoughtful and well-informed, and so the people we elect to be in charge of our governments are our best and brightest and most trustworthy.


## Why can we do better?

So how is it that this Ethereum thing has the potential to improve on this situation?

This post is meant mainly to motivate the discussion; the technical details aren't important here. (Maybe I'll write a post about that stuff in the future, because it's interesting, and because the devil is in the details – if you don't actually trust Ethereum to do what it's intended to do, none of the rest of this matters. But for now let's take it for granted.) So for now, the main points are:

  - it's a software platform, running out there on the Internet
  - where people can create apps that can run arbitrary code
  - that can do stuff involving money and ownership, as well as other kinds of data
  - and you can trust that code to run exactly as programmed
  - without needing to trust any particular person or organization.

That combination of attributes means that this is a platform that we can use to write code that handles stuff that is *valuable*. Not just financial stuff (although that's pretty neat on its own, and it's a prerequisite for a bunch of the other stuff), but also voting and governance and organizational-decision-making and so on.


## Contracts and smart contracts

One term used to describe the-thing-that-Ethereum-does is "smart contracts", so I want to take a moment to talk about regular legal contracts.

Contracts are a wonderful thing. I mean, everyone hates them, because they're inhumanly, intimidatingly formal. But they're an extremely useful tool in our toolbox of coordination mechanisms, especially now that we live on a planet with billions of people. Back when humans lived in 150-person tribes, we could use our natural social mechanisms to determine other people's trustworthiness and hold people accountable and resolve disputes; now that we live in cities of millions of people and constantly have to deal with strangers, we need a mechanism that's more formal. So we hire lawyers to write up our agreements in very-precise language, and we have courts to enforce those agreements, and this *enables us to cooperate with people we don't trust*.

Now, guess what kind of language is even more intimidatingly-formal and inhumanly-precise than legal language.

(Lawyer cousins of mine: that's right, my profession is coming to eat your profession.)

Ethereum-based "smart contracts" are written in a computer-programming language rather than in legalese. Smart contracts can carry out transactions involving cryptocurrency and other digital assets, as well as perform arbitrary calculations and do whatever kinds of actions we can make computers do. (And that doesn't mean that smart contracts are useless for actions that we can't completely automate yet; we can always just have the smart-contract delegate the task to the outside world by saying something like, "make sure that the person who owns account X clicks the button affirming that Y happened.") And just as we can hire lawyers to read the text of a legal contract and make sure that it seems fair and does what it's supposed to, we can have programmers audit the code of a smart contract.

(Note that smart contracts aren't contracts in any legal sense, but that's because they don't *need* to be; there's no need to "enforce" adherence to anything we can automate. The code simply does what it does.) (Although there are some interesting decentralized dispute-resolution systems being developed, like [Kleros](https://kleros.io/), for situations where we do need humans in the loop.)

And because this is all computerized and on the Internet, smart contracts are much more scalable than regular contracts. It's very hard to get a thousand people to sign a legal contract together, let alone a million. It's much easier to get that many people to click the button on the website and type in their password. So this opens up possibilities for coordination at large scales.


## So what kinds of problems are we talking about, again?

In the future I'd like to write up some more posts exploring each of these kinds of things in detail. But for now, here are some of the kinds of things that might be possible now/soon:

  - [Assurance contracts](https://en.wikipedia.org/wiki/Assurance_contract): "I promise to do X, as long as enough other people do too." In particular, this is great for funding public goods: "I'll chip in $20 towards the $1,000,000 goal, as long as enough other people do." (And the smart contract holds on to the money until the goal is met, and returns it to the donors if the goal isn't met by the deadline.) This is what Kickstarter does (although Kickstarter isn't blockchain-based), but the idea is more general than that; blockchains have the potential to allow us to make more kinds of *credible promises* (beyond just "I'll pay $N"), and that opens up possibilities for more kinds of large-scale "let's all jump at the same time" kinds of contracts.
  - [Token bonding curves](https://blog.goodaudience.com/rewriting-the-story-of-human-collaboration-c33a8a4cd5b8) are a mechanism for overcoming the "nobody wants to go first" problem, by creating incentives for early adopters. Actually, markets in general are a mechanism that often helps overcome the "nobody wants to go first" problem, because if you can predict in advance that something is going to be more valuable in the future, you can make a profit by investing in it early. The problem is that there are many situations in which we don't have a market even though one would be useful. Token bonding curves are an extremely lightweight way to create a "token" and an associated market for it.
  - [Quadratic funding](https://vitalik.ca/general/2019/12/07/quadratic.html) is a mechanism for taking a subsidy pool and deciding which public-good projects are the most worthwhile ones to allocate it to. The idea is similar to [donation matching](https://en.wikipedia.org/wiki/Matching_funds) programs that already exist, but the math determining the matching amount is different: a project that receives a large number of small donations will be given a larger subsidy than a project that receives a small number of large donations. (I'm not entirely convinced, but it does sound like a much better system than "let the politicians and bureaucrats decide.")
  - [Prediction markets](https://en.wikipedia.org/wiki/Prediction_market) are one of the best mechanisms we've got for predicting the future. (It turns out that people make more accurate predictions when they have to put their money where their mouth is.) Prediction markets could be an important component of creating *smarter organizations*. I don't think we've figured out yet exactly how these ought to be used, but one suggestion (called ["futarchy"](https://mason.gmu.edu/~rhanson/futarchy.html)) is to create organizations that automatically adopt whatever proposals are predicted to have a high likelihood of good results. Another (called ["holographic consensus"](https://medium.com/daostack/holographic-consensus-part-1-116a73ba1e1c)) is to create organizations that only vote on proposals that are predicted to pass (so that the organization can grow larger without being overwhelmed by the sheer number of proposals).
  - Decentralized Autonomous Organizations (DAOs): Blockchains offer us the opportunity to create organizations that have code baked into them (for the purpose of organization or decentralized-decision-making or whatever). Can we make organizations that can grow larger without becoming slow and ponderous and bureaucratic? Can we make organizations that can stay small while gaining some of the advantages of larger organizations? Can we make organizations that are *smarter*? I said earlier that governments are very appealing for the purpose of solving coordination problems because the whole idea is basically "let's put a coordinator in charge", which would solve a whole lot of problems if we had a coordinator who was actually competent and trustworthy; maybe, if we can create large organizations that don't suck so much, we can achieve that benefit without so many of the drawbacks.

This is all still very early days. We don't know yet what the mature versions of these technologies are going to look like. That's why this field is exciting: there's a lot of potential here, and there are opportunities for getting involved early in projects that might do a lot of good in the world.


## But couldn't this lead us all to our doom?

Yup!

As [Vitalik Buterin points out](https://vitalik.ca/general/2020/09/11/coordination.html), coordination isn't always good; it can be very bad if some subset of actors coordinate to the detriment of everybody else.

And as [Scott Alexander once said](https://slatestarcodex.com/2014/07/30/meditations-on-moloch/), if there *are* negative consequences to these technologies, we may not be able to uninvent them:

        The latest development in the brave new post-Bitcoin world is crypto-equity. At this point I've gone from wanting to praise these inventors as bold libertarian heroes to wanting to drag them in front of a blackboard and making them write a hundred times "I WILL NOT CALL UP THAT WHICH I CANNOT PUT DOWN"

So I'm definitely scared. But I also kinda feel like we're doomed anyway unless we do something drastic.

(That's a facile answer, but I think I really believe that. Many things in the world are going very well, and we should be grateful for that and be afraid of screwing it up. But there are also enough disasters on the horizon that I feel like we need to level up if we want to avoid them.)

The dream here is for us to be able to say, "Hey, let's all switch to this better way of doing things," or, "Hey, let's all fund this public good," and then (after a reasonable amount of discussion, to make sure it's a good idea and hammer out the details – which obviously are big scary steps that can easily go wrong, but part of the point here is that maybe we can become smarter and get those things right) it *actually happens*. If humanity had *that* ability, the world would look very different from the world we live in today.

In future posts I'd like to start exploring some of the specific topics/problems/projects mentioned above: token bonding curves, DAOs, etc. But for now, I hope this explains why I think this space is exciting.
