---
layout: post
title: Copy in Python
date:   2020-10-21T10:51:45+00:00
author: plonzari
categories: python
---

While there are probably thousands of book and web pages dealing with the issue after yet 
<a href="https://stackoverflow.com/questions/17873384/how-to-deep-copy-a-list"> 
another take </a> I just need a short reminder: there are three ways to copy an object in Python.


First we create a list <b> d </b>  with both two lists (<b> a,b </b>) and an integer <b> c. </b> 
Later we will see the relevance  of the repetition and of the mutable nature of the list type.

```python
a=[1,2]
b=[3,4]
c=5
d=[a,a,b,c]
print(a,b,c,d)
```

    [1, 2] [3, 4] 5 [[1, 2], [1, 2], [3, 4], 5]
    

We compare five ways to make copies in python.


```python
import copy 
d1=d
d2=d[:]
d3=list(d)
d4=copy.copy(d)
d5=copy.deepcopy(d)
```

There  really are  five copies of d:


```python
print(d1 == d,d2 == d,d3 == d,d4 == d,d5 == d)
```

    True True True True True
    

The operator <b> = </b> does not make a real copy of the list. It just 
gives another name to the same object:


```python
print(d1 is d,d2 is d,d3 is d,d4 is d,d5 is d)
```

    True False False False False
    
As a consequence changing an element in <b> d1 </b> is identical to changing 
 the element in <b> d, </b> and vice versa. The other copies are not affected.

```python
d[3]=6
i=3
print(d1)
print(d2)
print(d3)
print(d4)
print(d5)
```

    [[1, 2], [1, 2], [3, 4], 6]
    [[1, 2], [1, 2], [3, 4], 5]
    [[1, 2], [1, 2], [3, 4], 5]
    [[1, 2], [1, 2], [3, 4], 5]
    [[1, 2], [1, 2], [3, 4], 5]
    
Actually it is important that we have changed an element with an immutable type. Changing 
elements of the (sub)lists is propagated in all the first four copies. All these copies are called shallow.

```python
i=2
d[2][0]=7
print(d1)
print(d2)
print(d3)
print(d4)
print(d5)
print(d1[i] is d[i],d2[i] is d[i],d3[i] is d[i],d4[i] is d[i],d5[i] is d[i])
```

    [[1, 2], [1, 2], [7, 4], 6]
    [[1, 2], [1, 2], [7, 4], 5]
    [[1, 2], [1, 2], [7, 4], 5]
    [[1, 2], [1, 2], [7, 4], 5]
    [[1, 2], [1, 2], [3, 4], 5]
    True True True True False
    
The identity of the (sub)list is the same in <b> b, d, d1, d2, d3, d4 <b>

```python
b
```
    [7, 4]



The conclusion is that only <b> copy.deepcopy() </b>  duplicates everything, and all the
elements of <b> d5</b> are uncoupled from everything.


```python
d5[1][1]=8
print(d1)
print(d2)
print(d3)
print(d4)
print(d5)
i=1
print(d1[i] is d[i],d2[i] is d[i],d3[i] is d[i],d4[i] is d[i],d5[i] is d[i])
```

    [[1, 2], [1, 2], [7, 4], 6]
    [[1, 2], [1, 2], [7, 4], 5]
    [[1, 2], [1, 2], [7, 4], 5]
    [[1, 2], [1, 2], [7, 4], 5]
    [[1, 8], [1, 8], [3, 4], 5]
    True True True True False
    

The function deepcopy() is smart enough to copy the internal geometry though, and the first two elements are
kept identical.


```python
print(d1[0] is d1[1],d2[0] is d2[1],d3[0] is d3[1],d4[0] is d4[1],d5[0] is d5[1] )
print(d1[0] is d2[2],d2[0] is d2[2],d3[0] is d3[2],d4[0] is d4[2],d5[0] is d5[2] )
```

    True True True True True
    False False False False False
    

Going back to the beginning, the identity of the list elements is not changed by the copy process. 

```python
a=[1,2]
b=[3,4]
c=5
d=[a,a,b,c]
print(a,b,c,d)
d1=d
d2=d[:]
d3=list(d)
d4=copy.copy(d)
d5=copy.deepcopy(d)
i=3
print(d1[i] is d[i],d2[i] is d[i],d3[i] is d[i],d4[i] is d[i],d5[i] is d[i])
```

    [1, 2] [3, 4] 5 [[1, 2], [1, 2], [3, 4], 5]
    True True True True True
    
Beeing a mutable type, changing the value changes the identity of the forth element

```python
i=3
print(id(c),id(d[i]),id(d1[i]),id(d2[i]),id(d3[i]),id(d4[i]),id(d5[i]))
d1[i]=7
print(id(c),id(d[i]),id(d1[i]),id(d2[i]),id(d3[i]),id(d4[i]),id(d5[i]))
```

    1674940576 1674940576 1674940576 1674940576 1674940576 1674940576 1674940576
    1674940576 1674940640 1674940640 1674940576 1674940576 1674940576 1674940576
    

For an element with a mutable type deepcopy (and only deepcopy) changes the identity. 
This is consistent with the fact that now a change in values, because it does not change identities, is 
reflected in all the copies but the deep one.

```python
i=2
print(id(b),id(d[i]),id(d1[i]),id(d2[i]),id(d3[i]),id(d4[i]),id(d5[i]))
d1[i][0]=8
print(id(b),id(d[i]),id(d1[i]),id(d2[i]),id(d3[i]),id(d4[i]),id(d5[i]))
print(d1)
print(d2)
print(d3)
print(d4)
print(d5)
```

    1350457771080 1350457771080 1350457771080 1350457771080 1350457771080 1350457771080 1350456318664
    1350457771080 1350457771080 1350457771080 1350457771080 1350457771080 1350457771080 1350456318664
    [[1, 2], [1, 2], [8, 4], 7]
    [[1, 2], [1, 2], [8, 4], 5]
    [[1, 2], [1, 2], [8, 4], 5]
    [[1, 2], [1, 2], [8, 4], 5]
    [[1, 2], [1, 2], [3, 4], 5]
    
So the conclusion is that the assignment <b> = </b> gives another name to the same object, 
<b> =...[:], list() and copy()</b> create an entirely new object but do not create new copies of 
the (sub)objects, while  <b> deepcopy() </b> creates a new copy of the object and copies of  
all the  contained objects.

 Gist of the notebook with the above instructions:
 
<script src="https://gist.github.com/plonzari/936a8bbb4a925d879e055cae780e5bda.js"></script>