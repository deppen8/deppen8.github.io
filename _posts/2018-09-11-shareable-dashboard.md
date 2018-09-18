---
title: 'Building a shareable dashboard with Bokeh and Binder'
date: 2018-09-11
permalink: /posts/2018/09/shareable-dashboard/
tags:
  - Python
  - Bokeh
  - Binder
  - dataviz
---

In the spring, I was experimenting with visualizing spatial information in Python and was having good success with the [Bokeh package](https://bokeh.pydata.org/). Bokeh is great because it allows you to create interactive visualizations relatively quickly without needing to know JavaScript. Recent versions also handle GeoJSON data quite well which makes it easy to use with spatial vector data.

Something I had wanted to create for a while was a data dashboard for the survey element of our project. This would give us the ability to quickly see where artifacts of a given type were found or allow us to jump to a particular parcel to see what we had recovered there. Bokeh comes with a nice set of [widgets](https://bokeh.pydata.org/en/latest/docs/user_guide/interaction/widgets.html) that can be used for exactly this kind of dashboard, so it wasn't all that difficult to get it up and running.

As I built the app, it was always in the back of my mind that I would like to be able to share it with my collaborators. That, however, would mean getting it out of a Jupyter Notebook and on the web somehow. You see, the LEIA Project is a collaboration between a core group of archaeologists and an extended team of maybe a dozen or so specialists, both American and Spanish. Most of those people do not code and have no interest in getting anywhere near a Python script.

To use Bokeh widgets, however, one has to start up a [bokeh server](https://bokeh.pydata.org/en/latest/docs/user_guide/server.html). While there are a number of ways to do that, most of them would require my collaborators to use Python or for me to set up some complicated hosting system on a server. What I wanted was a method to put my widget app on the web for free without using anything but Python.

This spring when I hunted for a solution, I came up empty. I resigned myself to just running it locally from my laptop and showing it to my collaborators in person while I was in the field in Spain this summer.

After I returned to Seattle at the end of July, I decided to give it another go. I knew I couldn't be the only person who wanted to share my widget-based dashboard easily. So I turned to Twitter...

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Help? Need the right combo of tools to build a dashboard that:<br>- is free<br>- I can share with non-programmer colleagues without installing anything<br>- has widgets to query my dataset<br>- can produce an interactive map with the results of the widget query<a href="https://twitter.com/hashtag/gischat?src=hash&amp;ref_src=twsrc%5Etfw">#gischat</a> <a href="https://twitter.com/hashtag/Python?src=hash&amp;ref_src=twsrc%5Etfw">#Python</a> <a href="https://twitter.com/hashtag/rstats?src=hash&amp;ref_src=twsrc%5Etfw">#rstats</a></p>&mdash; Jacob Deppen (@jacob_deppen) <a href="https://twitter.com/jacob_deppen/status/1026932550843826176?ref_src=twsrc%5Etfw">August 7, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

... and Twitter delivered! 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">AFAIK some folks at scipy recently got Bokeh apps working on Binder, but I will have to go try to dig up a reference.</p>&mdash; Bokeh Plot Library (@BokehPlots) <a href="https://twitter.com/BokehPlots/status/1026935922468614144?ref_src=twsrc%5Etfw">August 7, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

As it turns out, while I was in the field in Spain, someone had solved this exact issue.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">For <a href="https://twitter.com/mrocklin?ref_src=twsrc%5Etfw">@mrocklin</a> at the <a href="https://twitter.com/SciPyConf?ref_src=twsrc%5Etfw">@ScipyConf</a> sprints: <a href="https://twitter.com/BokehPlots?ref_src=twsrc%5Etfw">@BokehPlots</a> servers on <a href="https://twitter.com/mybinderteam?ref_src=twsrc%5Etfw">@mybinderteam</a> <a href="https://t.co/NCd4MbSmyC">https://t.co/NCd4MbSmyC</a></p>&mdash; Min RK (@minrk) <a href="https://twitter.com/minrk/status/1018531306492383233?ref_src=twsrc%5Etfw">July 15, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

By following @minrk's example very closely, I was able to get my Bokeh app up on Binder in no time. With that, I could just send a link to anyone that allowed them to use my app in their browser.

If that is something you are interested in, the Binder team now has a nicely documented example in their [binder-examples](https://github.com/binder-examples/bokeh) GitHub repo. [Try it out!](https://hub.mybinder.org/user/binder-examples-bokeh-w0e7pr9k/proxy/5006/bokeh-app)

*Note: I have not included an example of my app here because the data aren't ready to be shared with the world yet.*