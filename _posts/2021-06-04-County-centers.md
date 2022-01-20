---
layout: post
title: Geographical center of Romanian counties
date:   2021-06-4T2:51:45+00:00
author: plonzari
categories: 
            - living
            - python
---

For those lacking travel destinations I have a map with geographical centers (centroids) of each Romanian county.
For the moment only latitude and longitude to be checked in 
<a href="https://www.google.com/maps/place/44%C2%B026'18.4%22N+26%C2%B005'30.1%22E/@44.43844,26.0895003,899m/data=!3m1!1e3!4m5!3m4!1s0x0:0x0!8m2!3d44.43844!4d26.091689 
"> Google Maps. </a>

{% include rocenter.html %}

For example the center of Bucharest seems to be one block north of Cismigiu Park.
Also <a href="https://www.google.com/maps/place/45%C2%B050'16.3%22N+24%C2%B059'12.6%22E/@45.8133843,24.9806131,2089m/data=!3m1!1e3!4m5!3m4!1s0x0:0x0!8m2!3d45.8378535!4d24.9868211 
"> my estimated centroid of Romania </a> is about two kilometers due north from the 
<a href="https://www.google.com/maps/place/The+Geographical+Centre+of+Romania/@45.8077024,24.9857011,1043m/data=!3m1!1e3!4m13!1m7!3m6!1s0x0:0x0!2zNDXCsDUwJzE2LjMiTiAyNMKwNTknMTIuNiJF!3b1!8m2!3d45.8378535!4d24.9868211!3m4!1s0x474ca3892fe7878f:0xcdbf099cb5794d8e!8m2!3d45.8059211!4d24.9881088 
"> "official" estimate</a>, 
south-east of the town of Fagaras. 

The error indicated above is likely to be a projection error. Indeed, the above calculations 
are made using planar coordinates, and overestimate the size of the northern parts of any surface. 
The real "spherical" centroid is thus always due south from our estimation. Also the largest 
planar county above is Suceava, while the county with the largest surface "on the ground" is Timis. 
The difference is entirely explained by their latitude.

<a href="https://nbviewer.jupyter.org/github/plonzari/blog/blob/gh-pages/_includes/ro-centroids-folium.ipynb 
"> A much less colorful version with code. </a>

Also, some ten kilometers south of the town of Fagaras, one can find the 
<a href="https://nbviewer.jupyter.org/github/plonzari/blog/blob/gh-pages/_includes/ro-circles.ipynb 
"> inner and outer circle centers. </a>
The inner circle center is the only point in Romania located more than 218km from any other country.
Similarly the outer circle center is the only point located less than 371km from any other 
point in Romania.

As an extra, I was exploring the application of the graph coloring ideas to the county map of Romania.
The map cannot be colored with three colors without having neighbors with the same color. 
As it is
<a href="https://en.wikipedia.org/wiki/Four_color_theorem"> well known </a> there is at least one coloring 
of the map with four colors. For the county's map there seem to be  millions of colorings, 
and below is an example with minimal usage of the forth color.

{% include ro-county-4.5color.html %}
