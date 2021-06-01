---
layout: post
title: Quantifying self, browser edition
date:   2021-05-30T2:51:45+00:00
author: plonzari
categories: living
---

Some time ago I modified a Chrome extension to track the time spent on individual web pages.
During the past year data for 80K visits to different pages on 3982 domains has been registered, 
together with the time actively spent on them.

Most pages are visited for a very short time, while there is a significant number of pages on which 
a much larger time is spent.  
{% include time_spent_hist.html %}

The histogram corresponding to the first few minutes shows a transition to a power law distribution 
around a few seconds.  

The distribution is more complicated but still compatible with a power law. The plot of the 
number of pages on which a time longer than $$t$$ is spent has power law tail consistent with
the histogram.

{% include time_spent_cd.html %}

The pure power law distribution is often called 
<a href="https://en.wikipedia.org/wiki/Pareto_distribution"> Pareto 
distribution </a>. Moreover the fact that  the number $$n$$ of most visited sites is proportional with
the inverse of the typical time,
$$\frac{1}{t}$$,  is known as <a href="https://en.wikipedia.org/wiki/Zipf's_law"> Zipf's </a> law.
This law also states that the time spent on the  $$i'th$$ most visited state decreases as $$\frac{1}{i}.$$

Something very similar happens if the times are accumulated for individual domains.

{% include time_spent_cd_domains.html %}




The time versus rank plot shows that there are a few sites on which a long time is spent. In fact I seem 
 to spend 95% of the time on less than 5% of the sites. This is similar with a less extreme 80%-20% 
 distribution called 
 <a href="https://en.wikipedia.org/wiki/Pareto_principle"> Pareto principle</a>. There are many 
 contexts in which this rule has been identified to hold. Indeed, most of the internet traffic 
 comes from a few pages, most of the Covid infections are related to few patients and 80% of 
 women appreciate only 20% of men (and probably vice-versa). The original 80%-20% rule observed by 
 Pareto for wealth distribution must be significantly more extreme these days. 
 
The list of the 20 domains on which  most of my time was spent shows that  I read too many news 
  search  compulsively for books I will never read and   and movies I will never have time to watch. 
  The first three sites nicely summarize my activity in front of the computer: reading news, 
  working on programming projects and watching movies.
    
  {% include Treemap.html %}
  {% include table_visited_sites.html %}
