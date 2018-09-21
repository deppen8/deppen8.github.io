---
title: 'Geohackweek highlights'
date: 2018-09-19
permalink: /posts/2018/09/geohackweek-highlights/
tags:
  - Python
  - Bokeh
  - Binder
  - dataviz
  - TremorViz
  - xarray
  - Geohackweek
  - UW eScience Institute
  - rppc
---

Last week I had the privilege of taking part in [Geohackweek](http://geohackweek.github.io/), a week-long event from the [UW eScience Institute](https://escience.washington.edu/) that brings together people from academia and industry to learn about and practice the latest developments at the intersection of data science and geospatial analyses.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Thank you to everyone who participated in <a href="https://twitter.com/hashtag/Geohackweek?src=hash&amp;ref_src=twsrc%5Etfw">#Geohackweek</a> and made it a great week! You can find video recordings of the 2018 tutorials here: <a href="https://t.co/qkdrvRnuWz">https://t.co/qkdrvRnuWz</a> <a href="https://t.co/LHWXW4t69h">pic.twitter.com/LHWXW4t69h</a></p>&mdash; UW eScience Institute (@uwescience) <a href="https://twitter.com/uwescience/status/1040713916093935616?ref_src=twsrc%5Etfw">September 14, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

The whole experience was wonderful, for which a mountain of credit must go to Anthony Arendt and the team of people who organized and led the hackweek, but here I wanted to focus on just a couple of things that were particularly valuable for me.

## Time to learn
For most people in academia, there is very little time (and little reward) for learning new technical skills. Usually we have to pick them up in order to achieve a very immediate goal. Edification for edification's sake is a rare commodity, so having an entire week set aside to do little besides try new things, fail, and learn with very low professional stakes was really satisfying.

## Group projects
About half of each day was spent on group projects. On the first day, some participants pitched general project ideas and recruited people to flesh out and work on those projects with them. [Because I have been thinking a lot about interactive data visualizations lately](https://deppen8.github.io/posts/2018/09/shareable-dashboard/), I joined three other participants to work on improving data visualizations of seismic tremor data. As someone who usually works solo on data science projects, it was enlightening to experience working with a team of people; I generally prefer group work over solitude. It was highly motivating to know I was making contributions that others could build from and improve. Even figuring out how to approach logistical challenges like managing our code with git/GitHub added a lot to my experience.

In the end, our original vision for a what our interactive visualization would look like was not quite achieved. But in the process, we learned a ton about visualization, particular packages, and their limits. We ended up producing two versions of the visualization, each with some of the original elements we desired. Major credit to our team lead, Ariane Ducellier, for getting a running version of the tool working using the Altair package. Our team GitHub repo, [ghw2018_tremorviz](https://github.com/geohackweek/ghw2018_tremorviz/), has her code as well as a [Bokeh version](https://github.com/geohackweek/ghw2018_tremorviz/tree/master/tremorviz_bokeh) I hacked together.

![tremorviz_bokeh](/images/blog/tremorviz.gif)

## xarray
On the more practical side of things, a tutorial from Joe Hamman introduced me to [`xarray`](http://xarray.pydata.org/), which I can imagine being very valuable to me in the future. I'd heard of xarray before, but only the name. I had no idea it could be so powerful for handling geospatial data.

The way I think of `xarray` is as a natural extension of `pandas` and `numpy`. xarrays have all the hallmarks of numpy arrays and matrices but with added capacity for labeling like a pandas DataFrame. This data structure is perfect for a lot of geographic data. Instead of converting a raster dataset to a numpy array and then engineering a way to track the geographic coordinates associated with each value in the array, xarrays allow you to keep the coordinates as labels, so that you can query and manipulate the data using the coordinates themselves.

I expect xarray will catch on and grow rapidly in popularity within the data science community. Numpy and pandas are so widely used that a package that borrows the best features from each is bound to find many useful applications. For my work, the ability to combine many kinds of data (artifact densities, elevations, hydrology, accessibility, visibility, etc.) from a study region into a single container (the xarray `Dataset`) while maintaining their geographic info is incredibly powerful.

## Reproducible Python Package Creator (rppc)
Don Setiawan introduced us to his [Reproducible Python Package Creator](https://github.com/lsetiawan/rppc) utility which makes turning code into an actual package much less painful. I wish I had known about this a few months ago when I was struggling to assemble my [`leiap` package](https://deppen8.github.io/posts/2018/09/python-packaging/)! I read countless blog posts and how-tos that all seemed to contradict one another. One blog would say *"Step X is absolutely vital"* while another made no mention whatsoever of this mysterious *Step X*. The `rppc` process simplifies everything enormously.

*(Note: Learning about Don's RPPC led me to discover [Cookiecutter](https://cookiecutter.readthedocs.io/), a tool that also creates Python packages, but most of the Cookiecutter templates seem a bit overkill for most scientific applications.)*



