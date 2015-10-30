# Automation for Developer Happiness

Kitt Hodsden

Slide: http://ki.tt/wd15

[@kitt](https://twitter.com/kitt)

Performance is everyone's problem

## What does _fast_ even mean?

* Key metrics
* Determine a baseline
* Start making changes
* Measure the effects

### Determining Key metrics

Be warned about quoted statistics.

You always want fast. But be gentle with yourself if it's not zippy fast.

We have a baseline we do not want to go over. (See Tim Kadlec's blog)

Case study: Etsy has great goals (total page load time, page weight, etc).

### Establish the baseline

You _should_ know how fast your site is. It's not hard: Open your browser, and
look at the timeline waterfall (Chrome DevTools is best).

[perfBar](http://wpotools.github.io/perfBar/) gives you a list of things you
should be paying attention to. If it's red, fix it.

"But it's fast for me" is a valid use case. But not the only one. You also have
mobile, etc.

You don't want to have to test for all of these different cases.

Enter Automation.

For Grunt, [start here](http://github.com/kitt/grunt-perf-template).

> A data point of 1 is the same as a data point of none: You don't know what
> anomolies happened.

[cssstats.com](http://cssstats.com) for nice stats on your css usage / size /
etc.

perfBudgets is good for automating running webpagespeed tests.

When it fails. Show it. Put it in people's face.

### Start making changes

Eg:
* _"Remove HTML comments"_
* _"Concatenate & minify CSS files"_
* _"I have 2MB of web fonts!"_
* etc

### Measure the effects

Re-run your tools to make sure you've fixed something.

[WebPageTest](http://webpagetest.org). You can even script logging into a page,
etc, for internal pages.

[WPTMonitor](http://www.wptmonitor.org) can track your WebPageTest results over
time.

### Bonus: Announce the effects

[sitespeed](http://sitespeed.io) or for a better looking WPT:
[run.sitespeed.io](http://run.sitespeed.io)

[How to d/l & install sitespeed](snk.ms/sswpt):

* Install Docker
* Start docker
* Pull the docker instances
* Start graphite
* Use Kitt's graphite config
* Start grafana
* Use Kitt's grafana config
* Log into grafana
* Seed a single metric run
  * Copied from Kitt's slides
* Setup the graphs
* Stick it in a cron job

[Try an Example](http://tiny.run:3000)

* `myuser` / `MY_SUPER_STRING_PASSWORD`
* `hi` / `hihihi`
