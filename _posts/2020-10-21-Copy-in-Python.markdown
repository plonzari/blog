---
layout: post
title: Copy in Python
date:   2020-10-21T10:51:45+00:00
author: plonzari
categories: Python
---

While there are probably thousands of book and web pages dealing with the issue after yet 
<a href="https://stackoverflow.com/questions/17873384/how-to-deep-copy-a-list"> 
another take </a> I just need a short reminder.

##### Create a list d with both mutable  (a,b - lists) and immutable (c - int) content 


```python
a=[1,2]
b=[3,4]
c=5
d=[a,a,b,c]
print(a,b,c,d)
```

    [1, 2] [3, 4] 5 [[1, 2], [1, 2], [3, 4], 5]
    

##### We test five different ways two copy the list


```python
import copy 
d1=d
d2=d[:]
d3=list(d)
d4=copy.copy(d)
d5=copy.deepcopy(d)
```

##### We really have five copies of d


```python
print(d1 == d,d2 == d,d3 == d,d4 == d,d5 == d)

```

    True True True True True
    

##### But the first is really shallow, as = does not make a real copy


```python
print(d1 is d,d2 is d,d3 is d,d4 is d,d5 is d)
```

    True False False False False
    

##### And changing an element of d changes d1, but not the others


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
    

##### Actually ways 2,3,4 are not full copies either.
##### Indeed the first four ways have copied only references to the member lists


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
    

##### And the change is propagated everywhere


```python
b
```




    [7, 4]



##### Only copy.deepcopy() duplicates everything, including references


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
    

##### deepcopy() also keeps the internal logic
##### as the first two elements of our list are identical


```python
print(d1[0] is d1[1],d2[0] is d2[1],d3[0] is d3[1],d4[0] is d4[1],d5[0] is d5[1] )
print(d1[0] is d2[1],d2[0] is d2[2],d3[0] is d3[2],d4[0] is d4[2],d5[0] is d5[2] )
```

    True True True True True
    True False False False False
    

##### Somewhat of a surprize:


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
    

##### The forth element seems to be initially the same everywhere


```python
i=3
print(id(c),id(d[i]),id(d1[i]),id(d2[i]),id(d3[i]),id(d4[i]),id(d5[i]))
d1[i]=7
print(id(c),id(d[i]),id(d1[i]),id(d2[i]),id(d3[i]),id(d4[i]),id(d5[i]))
```

    1674940576 1674940576 1674940576 1674940576 1674940576 1674940576 1674940576
    1674940576 1674940640 1674940640 1674940576 1674940576 1674940576 1674940576
    

##### This is because, as a immutable object the (int) type changes identity 
##### when changing value. A (list) object is mutable and does not change. Therefore
##### deepcopy copies identities of immutable types but changes the identities of mutable types


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
    

