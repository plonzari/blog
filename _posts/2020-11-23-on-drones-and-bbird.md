---
layout: post
title: On drones, helicopters and Blackbird
date: 2021-07-01T22:58:03+00:00
author: plonzari
categories: crafts
---
In a previouis [post]({{ site.baseurl }}{% link _posts/2020-11-23-on-drones.md %})
I discussed the physics of hovering drones and helicopters. My interest in the
physics of propellers was reignited by video discussing the possibility of a 
wind-powered vehicle to move faster than the wind (in the downwind direction). 

<div style="text-align: center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/yCsgoLc_fzI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

After searching the web a while I found quite a few places where the propeller equation is derived
and discussed, <a href="https://www.electricrcaircraftguy.com/2014/04/propeller-static-dynamic-thrust-equation-background.html 
"> like this one.</a> Unfortunately none of them are simple enough for me. They helped me
understand that my analysis was quite wrong. Fortunately my conclusions were not so bad.

Using the momentum change of the air under the action of 
the blades of size $$R$$ rotating at frequency $$f$$ and advancing with $$V$$, 
simple estimate of the thrust $$T$$ can be obtained as follows:

$$ T= K M (V_{displaced}-V_{relative}).$$ 

Here $$ M = \rho_{air} f R^2 p$$ 

is the mass of the displaced air while 
$$V_{displaced}=f p$$ and $$V_{relative}=V-V_{wind}$$. 
Here $$p$$ is the linear amount of air displaced by the blades rotating once, the 'pitch', and 
$$K$$ is some constant. For better agreement with data  <a href="https://www.electricrcaircraftguy.com/2014/04/propeller-static-dynamic-thrust-equation-background.html 
"> some assume</a> $$K=K(\frac{R}{p})$$ in order to take into account details of the aerodynamics.

For the case of the hovering drone/helicopter we have the following relations for thrust and 
power:

$$ T=K(\frac{R}{p}) \rho_{air} f^2 R^2 p^2, \quad P= L(\frac{R}{p}) \rho_{air} f^3 R^3 p^2 $$

A self similar propeller having $$\frac{R}{p}$$ constant and working at constant force would 
require a power 

$$P \sim \frac{\sqrt{F^3}}{R}$$ 

thus implying that the most efficient hovering is done with large propellers driven at low 
frequency. It should also be a large pitch propeller, given that $$\frac{R}{p}$$ is constant.

For the Blackbird driving downwind we have the thrust:

$$ T=K(\frac{R}{p}) \rho_{air} f R^2 p (f p - V + V_{wind}) $$

It is tempting to assume that the coupling between the propeller and the wheels which 
 $$f*d=V$$ ($$d$$ is also the length linking torque on the propeller
and linear force on the wheels) will reduce to $$f*p=V$$ in some reference frame. In this 
case 

$$ F=K(\frac{R}{p}) \rho_{air}  R^2  V V_{wind}  $$

which shows that it is the wind which drives the vehicle in front of it.  The relation 
$$f*p=V$$ could be the link to a geometrical 
interpretation of the movement Down Wind Faster than Wind mode of propulsion. As in the 
video above the propeller could be viewed as a wheel rolling on some track moving with the wind.
We use the symbol $$F$$ because this force driving the vehicle is not exactly the propeller 
thrust, and describes the action of the wind and the reaction of the wheels.
 

If I understand correctly the Blackbird can move both downwind and upwind. In the upwind direction 
the propeller acts as a wind turbine driving the wheels. The question is what happens if the 
land-yacht is stationary $$V=0$$. Which way does it go? The last formula implies that the force
is zero (small?) for stationary vehicles. Thus the $$V=0$$ state is an equilibrium one, but 
non-stationary. Small perturbations will start the motion. My guess is that the relationship between 
the pitch of the propeller and the mechanics of the wheel-propeller coupling will determine
which is the more probable mode. 


