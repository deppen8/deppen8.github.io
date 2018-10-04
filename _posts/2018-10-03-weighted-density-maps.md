---
title: 'Calculating and mapping weighted densities'
date: 2018-10-03
permalink: /posts/2018/10/weighted-density-maps/
tags:
  - dataviz
  - R
  - mapping
  - density
  - LEIA Project
---

Just a short post to document some work I've been doing lately to help our [LEIA Project](http://leiap.weebly.com/) team prepare for an upcoming conference presentation.

For the last couple of years, Marcos Llobera and I have been producing density maps of all of the different types of finds from our surface survey in Mallorca. Lacking good weighted density functions in Python, we wrote our analysis and mapping code in R, which has a little more facility with spatial densities.

It turns out that the density calculations are the easy part. Of the roughly 150 lines of code, only about 10 are directly related to calculating density. It's the map elements and especially the layout that have given me the most problems. In the end, we produced plots for all of our roughly 70 ceramic types, each with four different kernel sizes. Here are just a couple examples:

| North African amphorae | North African common ware |
|:----------------------:|:-------------------------:|
|![Àmfora Nord-Africana](/images/blog/Àmfora Nord-Africana.png) | ![Ceràmica Comuna Nord-Africana](/images/blog/Ceràmica Comuna Nord-Africana.png) |


If you find yourself looking at those two images and shrugging, I don't blame you. But if you know what your are looking at, you can see subtle but important differences between those two ceramic types.