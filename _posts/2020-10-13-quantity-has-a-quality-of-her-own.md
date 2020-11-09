---
title: Quantity has a quality of her own
date: 2020-10-13T22:58:03+00:00
author: plonzari
layout: post-with-mathjax
categories: Politics
---
By talking to a few hundred senators 
<a href="https://en.wikipedia.org/wiki/Carthago_delenda_est" data-type="URL" data-id="https://en.wikipedia.org/wiki/Carthago_delenda_est">Cicero was able to start a war</a>. Luther has done it by <a href="https://en.wikipedia.org/wiki/Ninety-five_Theses" data-type="URL" data-id="https://en.wikipedia.org/wiki/Ninety-five_Theses">nailing a piece of paper to a door</a> 
and Hearst <a href="https://en.wikipedia.org/wiki/Propaganda_of_the_Spanish%E2%80%93American_War" data-type="URL" data-id="https://en.wikipedia.org/wiki/Propaganda_of_the_Spanish%E2%80%93American_War">with a journal</a> 
with maybe 100000 readers. Radio and television have been considered big revolutions in opinion forming. 
It is thus reasonable to wonder if the changes caused by social media are something new, different from the past. 
On the one hand the past shows a more or less gradual increase in the speed and strength of  information dissemination and opinion-forming. 
The present folows this quantitative rule but, on the other hand, it could also be qualitatively different.

There are many models for opinion-forming (rumor-spreading) but the one I like most is based on the well-known 
Ising model. See for example 
<a href="https://www.cl.cam.ac.uk/techreports/UCAM-CL-TR-767.pdf" data-type="URL" data-id="https://www.cl.cam.ac.uk/techreports/UCAM-CL-TR-767.pdf">Ising model of rumour spreading in interacting communities</a>, 
by Ostili et al. The model is simple: the  distribution of beliefs of a population choosing between two opinions 
$$  O=1 $$ and $$O=-1$$ is modeled by minimization dynamics of an energy function

$$  E=-J \sum_i \sum_{j\in N_i} O_i O_j. $$

This formula models a tendency of  people to adopt similar opinions with those they are in contact with 
(their neighborhood).
If the neighbourhood  $$N_i$$ is small the population contains many small communities of like opinion. But beyond a 
certain size of neighborhoods one can have situations in which there is only a small number of communities and everyone 
in the same community has the same opinion. Moreover the transition can be sudden.

<div style="text-align: center">
<a href="https://twistedphysics.typepad.com/cocktail_party_physics/phase_transitions/">
<img src="{{ site.baseurl }}/assets/images/ising.png" width="500" /></a> 

 <p>  <em> Ising agents with three increasing neighborhood sizes (interaction strengths)</em></p></div>

A conclusion of such an analysis would be that, assuming the neighborhood size has increased constantly in the past, 
it is possible that the opinion forming dynamics have changes drastically at a certain point in time, probably quite 
recently. At this point many measurable variables could have drastically changed. For example the average number of
people one knows (talks to) having a different opinion would drop to almost zero. We do not really know if this is 
the case and it is difficult to go back in time and measure.

A similar physically inspired model of social dynamics is beautifully presented as a  
<a href="https://ncase.me/polygons/"> Parable of the Polygons </a>.

