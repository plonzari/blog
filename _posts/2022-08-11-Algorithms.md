---
layout: post
title: Algorithms
date:   2022-08-11T00:51:45+00:00
author: plonzari
categories:
            - python
---
After a few months of more or less diligent study I finished "consulting" three great resources for
learning about algorithms: <a href="https://www.algorithmsilluminated.org/"> 
 Algorithms Illuminated book series by Tim Roughgarden,</a> 
<a href="https://www.amazon.com/Introduction-Algorithms-3rd-MIT-Press/dp/0262033844"> 
 Introduction to Algorithms, by Corben et al.</a> and 
<a href="https://web.stanford.edu/class/cs168/index.html"> 
 the Stanford course CS 168: The Modern Algorithmic Toolbox.</a> I was not diligent enough to do the homeworks and solve
all the proposed problems but I followed all the arguments and most proofs.
 
The most important thing one learns from such resources is how and where to look for a good algorithm if the need 
arises. But for me the most surprising thing  have been the *data structures*. 
<!--more-->
My formal computer science studies have stopped at lists (stacks and queues, not even dequeues). I have been surprised 
to learn about the multitudes of other very useful data structures. It seems that being able to find the right data 
structure for your problem is as useful as finding the right algorithm, and is the other most practical skill one can get
from formal computer sciences.

Below I make a list of the most surprising (though sometimes obscure) data structures I encountered.

1. <a href="https://en.wikipedia.org/wiki/Bloom_filter"> Bloom filters</a> 

2. <a href="https://en.wikipedia.org/wiki/HyperLogLog"> HyperLogLog</a>

3. <a href="https://en.wikipedia.org/wiki/Disjoint-set_data_structure"> Y-fast trie</a>

4. <a href="https://en.wikipedia.org/wiki/Disjoint-set_data_structure"> Union-find</a>

5. <a href="https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type"> Conflict free replicated data type</a>

6. <a href="https://en.wikipedia.org/wiki/Order_statistic_tree"> Order statistic tree</a>

7. <a href="https://en.wikipedia.org/wiki/Interval_tree"> Interval tree</a>

I also enjoyed 
<a href="https://news.ycombinator.com/item?id=32186203"> this HN discussion</a> where one can find tons of other data 
structures. As always there should be another side to the coin: these data structures seem to be designed to minimize 
memory size and/or algorithmic complexity. These days memory access 
<a href="https://blog.cloudflare.com/when-bloom-filters-dont-bloom/"> could often turn out to be the bottleneck.</a>
