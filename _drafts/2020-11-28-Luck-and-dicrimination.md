---
layout: post
title: Luck and discrimination
date: 2020-11-28T09:58:03+00:00
author: plonzari
categories: numbers
---

In very competitive situations where a small numbers of winners are chosen out of a large number of competitors,
small amounts of luck or discrimination can change significantly the results. The idea of the analysis 
below comes from a very interesting video by <em> Veritasium: </em>

<div style="text-align: center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/3LopI4YeC4I" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

The main idea is actually very simple: when there are many competitors and the winners are selected on the 
basis of some score, the differences between the highest scores can be very small. One can always hope that 
this score is is an objective measure of skill and ability but even the smallest measure of luck and/or 
discrimination between the competitors can change the winners pool. This can be explain why, for example,
even though the proportion of women with STEM degrees approaches parity, the academic jobs are still male 
dominated. It is a discouraging  mathematical explanation but one has to take into account another aspect: 
if substantial efforts are not taken to eliminate luck and discrimination in such competitions, then 
it is not the very best which are selected. 

Let us illustrate the problem with a simple model. Suppose that we have a competition with large $$N$$
participants. Apriori the scores $$x$$ of each participant have a probability distribution $$P(x)$$

Each participant has a small amount of luck or discrimination which changes the score to
$$y_i=x_i \pm \epsilon$$ with a small amount  which can be positive or negative, uniformly distributed. 
The best  $$M\ll N$$ scores will win the competition.

If we compute $$P(n,M,N)$$ the probability that there are $$n$$ unlucky  
$$ P(n,M,N)= \frac{N!}{2^{N+1} n! (M-n)! (N/2-n)! (N-M-N/2+n)!} n \int_0^\infty dy 
\left[ A+B \right] $$

$$A= P(y+e) Q(y+e)^{N/2-n}Q(y-e)^{N-M-N/2+n} (1-Q(y+e))^{n-1} (1-Q(y-e))^{M-n}$$

$$B= P(y-e) Q(y+e)^{N/2-n}Q(y-e)^{N-M-N/2+n} (1-Q(y+e))^n (1-Q(y-e))^{M-n-1}$$

