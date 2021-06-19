---
layout: post
title: The interviewer's solution
date:   2021-06-19T0:51:45+00:00
author: plonzari
categories: 
            - living
---

Recently a very interesting problem came to my attention. It is extremely interesting given that 
it can have practical applications for many real life decisions.

Suppose that you have to find a good candidate for a job. The candidates are interviewed one at a time,
each interview has a fixed cost $$c$$ and each candidate can give a gain $$X_i$$ to your firm, drawn
from some distribution. After each interview an irrevocable decision to hire or not the candidate 
must be taken. The problem is finding the strategy that maximizes the gain. 

<a href="https://en.wikipedia.org/wiki/Optimal_stopping"> According to Wikipedia </a>
 this is an example of a stopping problem, sometimes called "secretary problem", clearly so called 
 because (re)introduced by some "Mad Men" in the 60's.
  
In many cases the best strategy seems to be passing the first $$T$$ candidates and then hiring the 
candidate that is the best with respect to those interviewed before. The value of the threshold depends on the details of the problem. 
For negligible interview cost and uniform distribution of candidate gains,
 $$T$$ is the closest integer to $$\sqrt{N}$$  where $$N$$ is the number of candidates. 

Sometimes the strategy is called the $$37\%$$ rule because the threshold that ensures the highest
probability to find the best candidate is larger (for more than 7 candidates), $$T=\frac{N}{e}$$.

I do not know the result for the problem above where the cost of an interview cannot be neglected 
and when some information is known about the distribution of $$X$$. The solution must be out there.

The problem can be relevant in many situations: job search, apartment search, parking at the mall
or  even dating. Of course, real life is always messier but psychological studies show that people
often stop too early. I would be curious how often hires are done in this sequential manner and 
how many managers do know the rule. From a game perspective probably it is best for a candidate
 to be late in the interviewing process. Maybe there is a relation with the anecdote of the
 manager that throws away half the applications with a simple explanation: 
 'We do not hire unlucky people.' 


