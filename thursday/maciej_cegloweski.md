# The Website Obesity Crisis

Maciej Cegloweski

[@pinboard](http://twitter.com/pinboard)

This isn't about shaming anyone.

## The problem

The overweight web: Average web page size is up 15% in 2014. Just shy of 2MB.

By 20/20, articles about web bloat could be 5MB or bigger.

Defining Deviancy Down.

Your contents website shouldn't be bigger than the size of the works of Russion
Literature.

A 400 word Medium post is larger in size than the entire book "Crime And
Punishment".

^^ That shouldn't be happening.

Article: A (Not So) Brief History of page size through 2015 (yodda?)

Can we have a visual idea of how heavy a page is? Maybe the sides of the browser
bow out?

Tim Dadlec "can't risk performance".

## Solutions?

* Facebook's Instant Articles
  * Announced on a 6.1MB site, who only links to a 41MB video.
  * internet.org: 2/3 of the world can't be connected. Yep, it's got a 16MB
    movie in the background
* Designers that do this, must use the Apple Hockey-puck mouse as punishment
* Google's AMP
  * Announced on a page that is theoretically infinite. The carousel gets loaded
    over and over and over again. It re-downloads a 3.4MB video over and over

## The William Howard Taft's Tax

If your designs look better with images replace by those of Taft, then you
probably don't need them.

But... If it looks better with Taft there, maybe you should leave Taft in.

## Actual solution

1. Send the critical stuff to the user first
1. Stop.
  * Seriously; they already have the critical stuff you said they need

## Everything is "fine"

Devs come up with things to convince themselves that "everything is fine".

Eg; Speed Index.

The only honest measure is from the request through to the user has clicked to
close the last ad.

Why turn in the wing mirrors on your big SUV to save some fuel when you could
ride a bicycle.

## The web Pyramid

```
/\
/ Scripts \
/-------\
/ Images \
/-------\
/ Markup \
/-------\
/ Text Worth Reading \
---------
```

[Image]

## Fat Ads

12.1MB down to 1.1MB by enabling Ad Blocker on site about how Ad Blocking is
hurting publishers.

The "Marketing Landscape" in 2015 has 1876 companies.

Advertisers say "This is how it has to be".

But: Advertisers are liers. Literally; their job is to convince you to do
someting you wouldn't normally want to do.

And they tell us this bloat is the cost of getting your stuff for free.

The "Opportunity" (aka: Problem) is investors keep propping up the ad serving
networks in the hopes they'll get a bigger return in the future.

### Can we regulate it?

* Ban 3rd party ads & tracking
  * Ads on the site are ones we've purposely designed into it
  * "But we _need_ surveilance!"
    * They're not even using it (or at least ineffectively)

Calculating the cost of bandwidth to load ads. `boston.com` costs around $0.32
to load all the ads on the page.

### Put it in last

For "Performance".

You really have no idea what they're goin gto do.

It's like having a party, everyone is having fun, then a salesman barges in and
demands everyone sits down so they can buy tupperware.

### Dumb Ads

The old way of doing dumn ads worked great for us. Why can't they work again
today?

## Fat Assets

Eg: Huge hero images.

We don't notice because we have fast internet at home / in the office.

But Chrome can be smart enough (`srcset`) to request a different image. So, how
do the designers even know what'll be requested?

Example: "Chickenshit Minimalism" - by maciej. It's 1.4MB large! Why? Because
there's a hidden image that can't even be found unless you dive into the footer.

## Design

Example: Verge's "Apple Watch Review". Everything happens on scroll except what
you'd expect: Scrolling through a document.

A Calendar select where the dates are huge, and the actual info is tiny

Conversely: Going from an information rich, easily sorted design to a minimal
information, can't be sorted, naggy headers, etc (eg; Paypal's history page)

Docker homepage:
* Illegible tabs
* With vast whitespace between them
* Where's the actual content?

## Responsive Design

Often don't know their own design - hamburger menu pop-out doesn't fit with the
design. And what's with that huge ad at the top? etc

## Cloud

### Amazon

Analogy:

> We guarantee the freezer will never defrost. Buuuut, the handle might get
> stuck for hours of a time. So, when cooking, take that into account.

Layers upon layers upon layers get added on.

Devs love to play with it.

Complexity is a bug lamp for people.

But it happens on the frontend too, not just the backend.

Example: 235 times faster to use a shell script than the "distributed" hadoop
solution when solving chess moves.

| | Pinboard | ACME
| ----- | -----
| Daily Users | 8k | 3k
| Employees | 1 | 1
| Revenue | 12K | 5K
| Hosting | 1K | 23K
| Income | 11K | (18K)

## What's next for the web?

2 possible futures:

* Minecraft style:
  * It's blocky, and will never look beautiful
  * But you can build anything you want with it
  * It's super open
* The FPS style
  * Looks beautiful
  * But you can't really do much other than exactly one thing
  * And you can't change it; you can only opt out.

> I want us to commit to the idea that as computers and the network gets faster,
> the internet gets faster.
>
> And let's break the back of the surveilance culture.
> We have the power to change it by doing our own thing; by being independent.
> We just have to stand together.
