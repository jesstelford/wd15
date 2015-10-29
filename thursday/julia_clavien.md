# Cognitive Bias in Software Development

Julia Clavien

[@juliaclavien](http://twitter.com/juliaclavien)

Devs aren't perfect. A rockstar dev team doesn't mean they wont make mistakes.

> Systematic errors in judgement and decision making common to all human beings

- Daniel Kahneman

1. The Planning Falacy
1. Group Think
1. Confirmation Bias
1. Hyperbolic Discounting
1. Sunk Cost Fallacy

## The Planning Falacy

Case stude: Sydney Opera House

* Estimated $7MM
* Final cost $102MM

15x over original estimate! Whoa!

Clients still want top level estimates

Devs think they're pushing a boulder up hill.
Clients think the devs are coding monkeys

> The tendency of individuals to display an optimism bias and underestimate the
> time and resources required to complete a project

*Motivated Reasoning*:

Are all the incentives in the right place to get the correct estimates in the
first place?

*Planning focalism*

> The tendency of individuals to perfceive th especific task of project to be
> copmleted as unique, and ignore th etime needed to complete similar tasts or
> projecs in the past.

When we ignore past lessons, we continue to fail. Things such as:

* Known knowns
  * eg; "Tom will be away next week"
* Known Unknowns
  * eg; I know I don't know this part of the spec because it's missing
* Unknown Unknowns
  * _Reference lass forecasting_ (by Bent Flyvbjerg) can help
    * Don't get caugh tup in the details. Instead, use a reference class to
      forecast against

Postmortems are good, but try a _premortem_ next time!

* Imagine you're in the future. Now, what went wrong?
  * Unlocks thinking to surface what you haven't thought of
  * Legitimises doubt. Making doubt an important tool.
  * Low cost, high reward.

## Group Think

aka:
* Herd mentality
* Bandwaggon

Every one kind of nods along. They just concur.

Can result in lower quality decisions being made.

How can we reduce that?

* Solicit opinions in advance
  * People are more candid before you get everyone into a room
    [usecandor.com](http://usecandor.com)
* Blind voting
  * Even when you think it's not necessary

## Confirmation Bias

Our tendency to interpret things in a way that suits our preconceptions.

Eg: "Where's the nearest apple store?" - "Kent St, they just released the iPhone
6!". "No, I meant apples the fruit!"

* Flip The Frame
  * Instead of asking "Is X true?", ask "Is the opposite of X false?"
  * Assign a Devils Advocate role - they must always give the opposite opinion
    * Wear some costume devil horns

## Hyperbolic Discounting

[Sad Panda.]

* "I'm definitely going to come back and document this later"
* "I'll come back and do this refactor soon"

But... you never do.

Technical debt builds and you pay interest on it.

> The tendency to prefer smaller payoffs now, over larger payoffs later. This
> can lead to discounting the future value when it requrest sacrifices in the
> present.

Eg: Did a manager at Apple Maps think "It's ok, we'll come back and add in those
roads later..."?

* Pause and share
  * Actually confront when you think you're doing the discounting

## Sunk Cost Fallacy

How often have you been working on a codebase, and you know it's a dead end, but
you keep trying so hard? That's it.

> The tendency of individuals to base deisions on honouring previously expended
> costs, rethat than on the future consequences.

[cute pug]

Why? We don't like feeling stupid (eg: Admitting it was the wrong approach)

* Get clear on options and outcomes
  * "Am I considering future consequences only, or am I looking also at past
    expended effort?"

## Q&A

*Example of a premortem?*

Get the right people in a room. Make it a safe space to talk about the issues.

"Let's imagine we're in the future", then let people break out and come up with
their own thoughts. Bring it back as a shared thought, and drive the discussion.

*Hyperbolic Discounting vs an MVP?*

It's relative to the size of the project. If you're going to throw out the MVP,
then it doesn't matter. If the projec tis really small with small impact, you
don't need to worry so much.
