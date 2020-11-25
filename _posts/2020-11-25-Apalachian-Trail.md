---
layout: post
title: Politics on the Appalachian Trail
date:   2020-11-25T2:51:45+00:00
author: plonzari
categories: politics
---

Inspired by the observation

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Out of the roughly 2200 miles, 445.6 are in red states, not counting the 20 miles on the border between West Virginia and Virginia. Dare I go county by county in the blue states and get a 2021 political map of the AT?</p>&mdash; Codruța Morari (@CodrutaMorari) <a href="https://twitter.com/CodrutaMorari/status/1331352896521310208?ref_src=twsrc%5Etfw">November 24, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
I have decided to play a bit more with
<a href="https://plotly.github.io/plotly.py-docs/generated/plotly.express.choropleth.html"> 
<code>plotly.express.choropleth</code>. </a>

Along the Appalachian trail I count 85 counties in 14 states. 
According to some preliminary  results 16 of those counties have gone to Biden, so the trail is quite red.
Trump has won with an average of 63%.

{% include AT_votes.html %}

Nevertheless, with 2260624 votes Trump gets only 54% of the popular vote along the trail.
This difference between the average of percentages and popular vote is quite common for US elections.

Obviously, one would still expect the rural areas on the trail to remain very red, but the urban areas are shifting. 
Plotting the differences between the percentages of Biden and Clinton one can see a clear blue trend.

{% include AT_diff.html %}

Even at this scale some of the main features of the 2020 elections are clearly apparent: GA, PA and NC
getting blue and Upstate NY going red. 
  


