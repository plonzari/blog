---
layout: post
title: Vaccine efficacy redux
date: 2021-08-09T22:58:03+00:00
author: plonzari
categories: numbers
---
In a previous [post]({{ site.baseurl }}{% link _posts/2020-11-23-Vaccine.md %})
I analyzed the data from the Moderna and Pfizer vaccines trials. Recent data from the romanian 
autorities allows us to estimate values for the vaccine efficacy which are significantly lower 
than what was measured in the trials.

Latest data show that about 80% of the hospitalized patients and 90% of the dead are unvaccinated.
The vaccine efficacy can be expressed as $$V_e=1-\frac{p_v}{p}$$ where $$p$$ ($$p_v$$)
are the incidences of hospitalizations or deaths in the vaccinated (unvaccinated) populations.


Given the fact that the rate of vaccination is approximately 25% 
the proportion of vaccinated patients in the hospital satisfies

$$\frac{p*.75}{p*.75+p_v*.25}=.80.$$

This implies a much smaller than predicted hospitalization efficacy $$V_e=.25.$$ Protection against 
death is higher ($$V_e=.66$$) but far from absolute. 

Probably better data will increase these estimates but not enough to approach even the lowest 
estimates one can find ($$.6$$ efficacy in preventing hospitalization). Many experts blame the 
lower efficacy on the prevalence of
the new virus variant(s). My guess is that most of the difference is due to increasingly dangerous 
behaviour of the vaccinated and the fact that those exposed to an increased risk of infection 
should be less hesitant to vaccinate. 

I expect in the future that more data and a better vaccine coverage will show higher effective 
efficacy. There will also be a public health communication problem as the proportion of 
vaccinated between the COVID hospitalizations and deaths can only increase.

