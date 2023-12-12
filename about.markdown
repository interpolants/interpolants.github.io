---
layout: page
title: Overview
permalink: overview
---

Let's lay out the groundwork for building generative models out of dynamical transport. From there we can see what interpolants facilitate. 

We start with the following setting. Suppose you have samples taken from two distributions with density $$ \rho_0(x_0)$$ and $\rho_1(x_1)$. Let's choose simple examples for what these densities could be, though in general we stress that they could be arbitrary. For now we'll say that any $x$ exists in $\mathbb R^{d=2}$, that $\rho_0$ is an N$(0,1_{d=2})$, and that $\rho_1$ is some complicated $2$-d density like the checkerboard one presented here.


<div style="text-align: center;">
<img src="assets/figs/rho0.svg" alt="Alt text for the image" width="300"/>
<img src="assets/figs/rho1.svg" alt="Alt text for the image" width="300"/>
</div>

With these two densities in hand, we will be motivated by the following question:
<div class="centered-text-box">
<span class="colorful-frame">
What is a suitable way to map samples from one density to samples from another?
</span>
</div>

We will consider this parametrically -- can I learn this map? There are some key features that we are certain to want in this parametric setting:
- We can efficiently *learn* the parametric realization of the map.
- Our parametric class is expressive enough for the true map to be captured by it. 

In what follows, we detail a paradigm to that allows for defining a broad family of such maps through the use of what we call a *stochastic interpolant*. From there we'll see what type of learning problem we can set up to facilitate this with neural networks. Along the way, we'll draw connection to score-based diffusion [(Song et al. 2021)](#song-2021) as well as denoising methods [(Ho et al 2020)](#ho-2020). 



### Connecting $\rho_0$ to $\rho_1$

When thinking about dynamical transport between $\rho_0$ and $\rho_1$, we can take two perspectives: the Eulerian viewpoint, in which we ask about the time dynamics of *intermediate density* $\rho(t,x)$, and the Lagrangian viewpoint, in which as about the transport of *individual samples* from an initial density (e.g. $\rho_0$). 

Let's start with the former, the Eulerian perspective. Under what rule must $\rho(t,x)$ evolve so that at time $t=0$, our time-density is equal to our initial density $\big(\rho(t=0, x) = \rho_0 \big)$, differentiating between the two with an underscore) and at $t=1$, it arrives at our final density $\big(\rho(t=1,x) = \rho_1$)\big)? Because a probability density is a conserved quantity, we can describe its dyanmics via a *continuity equation* (also called a transport equation sometimes):

$$
\partial_t \rho(t) + \nabla \cdot \mathbf{j} = 0
$$

where $\nabla$ is the divergence operator and $\mathbf j$ is a *current density* (also called a flux density) describing how the probability mass is moving through a unit area, the divergence of which characterizes the dynamics of the change in measure. I have dropped the $x$ from $\rho(t,x)$ to shorten the notation. Because $\rho(t)$ is a conserved quantity, the divergence of the current density and the time dyanmics of $\rho(t)$ must counter balance each other.

When the current density $\mathbf j$ can be characterized by a velocity field $b(t,x)$ and 

##### Below
- animation of eulerian vs lagrangian (density change versus prob flow lines) for simple 1D system
- Ask how do we learn $b$? 
- Introduce interpolants, general and with examples
- show that it allows us to sample $\rho(t,x)$ everywhere (e.g. with example you had above)
- Through which we can learn $b$.
- 

A relevant extension of this 

here is my test for a codeblock:

```python
def hello_world():
    print('Hello, world!')
```

#### References
1. <a id="song-2021"></a>Yang Song, Jascha Sohl-Dickstein, Diederik P. Kingma, Abhishek Kumar, Stefano Ermon, Ben Poole. Score-Based Generative Modeling through Stochastic Differential Equations. *ICLR 2021*

2. <a id="ho-2020"></a>Jonathan Ho, Ajay Jain, Pieter Abbeel. Denoising Diffusion Probabilistic Models. *ICLR 2021*



<!-- This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/) -->

<!-- You can find the source code for Minima at GitHub:
[jekyll][jekyll-organization] /
[minima](https://github.com/jekyll/minima) -->

<!-- You can find the source code for Jekyll at GitHub:
[jekyll][jekyll-organization] /
[jekyll](https://github.com/jekyll/jekyll) -->


<!-- [jekyll-organization]: https://github.com/jekyll -->
