---
layout: post
title: Quantifying self, browser edition
date:   2021-05-30T2:51:45+00:00
author: plonzari
categories: living
---

Using a Chrome extension I managed to gather about 80K visits to different pages on 3982 domains
and times spent active on these pages over the past few months.

A histogram of the number of different domains as a function of the total time spent on pages belonging 
to the domain show a large majority of domains are visited for a short time. 
{% include time_spent_hist.html %}
 The time versus rank plot shows that there are a few sites on which a long time is spent. In fact I seem 
 to spend 95% of the time on less than 5% of the sites. This is more extreme than the usual 80%-20% of the 
 Pareto principle.
 
{% include time_spent_cd.html %}
The distributions seem to be of the power-law type. The blue and the green curve 
(visible in the upper left corner) correspond to the related Pareto and 
<a href="https://en.wikipedia.org/wiki/Zipf's_law"> Zipf's </a> laws. To recap, 
in this case Zippf's law states that the time $$t$$  spent on the $$i'th$$ most active domain 
decreases as $$\frac{1}{i}.$$ This  different from the above mentioned Pareto principle. 

While for most domains my distribution seems to be less extreme than the standard Zipf and Pareto cases,
the 2-3 most visited domains cover a third of my browsing time, while the 20 most visited sites are responsible 
for  two thirds of the time I loose online.

  {% include table_visited_sites.html %}
