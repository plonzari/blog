---
layout: post
title: On drones, helicopters and Blackbird
date: 2021-07-01T22:58:03+00:00
author: plonzari
categories: crafts
---
[Link to a post]({{ site.baseurl }}{% link _posts/2020-11-23-on-drones.md %})
After playing a bit with a DJI Mavic Air drone I started to wonder what are the differences between the physics of 
drones and helicopters. One particular question is which one would be better to hover with given weight. Also
how long can a drone and/or helicopter fly (hover)?

These questions have a lot to do with the type of engine and details of propeller aerodynamics. As I did not find
simple and relevant references I will try a simple physical analysis.

Let us consider a wing modelling a blade of the propeller, moving in the horizontal plane. Quantities of interest are 
the vertical force on the propeller $$F$$, the speed at which the wing section moves $$v$$, the angle of attack 
between the wing and the horizontal $$\alpha$$ and the power $$P$$ used to move the propeller against the drag.
For a section of wing of size $$dr$$ along the wing/blade one has:

$$ F = F_p * \cos(\alpha), \quad P= v * F_p *\sin(\alpha).$$

$$F_p$$ is the force perpendicular to the wing $$ F_p=K v \sin(\alpha) $$, with $$K$$ some constant. 
These equations must still be some approximations, the trigonometric functions probably only qualitative 
descriptions. Anyway, for a propeller blade rotating with angular speed $$\omega$$ we have

$$ dF=K_1 \omega r dr \cos(\alpha) \sin(\alpha)$$ and  $$dP=K_2 \omega^2 r^2 dr  \sin^2(\alpha)$$

At least we have something reasonable. When the blade is horizontal both the lift force and the power are zero. 
If the blade is vertical the power is maximal, while the lift force is again zero. Integrating over the length of 
a blade 

$$ F=A \omega R^2 \cos(\alpha) \sin(\alpha)$$ and  $$P=B \omega^2 R^3  \sin^2(\alpha)$$



Again, $$K_i, A,B $$ are some constants that could take into account some of the complexities of the blade 
geometry and aerodynamics.

At fixed $$\alpha$$ let us think how we can minimize $$P$$ at constant $$F$$. We can derive 
$$P=C \frac{F^2}{R \cos^2(\alpha) }$$. So, to hover with minimal power one needs large blades (wings) turning slowly
($$\omega\propto \frac{F}{R^2 \sin^2(\alpha)}$$). Maybe something with very large propeller blades, limited by other engineering
requirements would be better. Like in this example of human powered helicopter:

<div style="text-align: center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/zDq10GsbVJU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

A similar analysis keeping $$R$$ constant would let us conclude that blades with very low angle of attack spinning fast
would be the best solution. To be followed.  