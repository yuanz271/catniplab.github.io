---
layout: post
title: Spatiotemporal Dynamics and Reliable Computations in Recurrent Spiking Neural Networks (2017)
category: journalclub
olddate: April 12, 2017
---

* [Paper](https://arxiv.org/pdf/1611.01557.pdf) Ryan Pyle and Robert Rosenbaum,  Spatiotemporal Dynamics and Reliable Computations in Recurrent Spiking Neural Networks, Physical Review Letters, 118, 018103 (2017)

* Abstract

Randomly connected networks of excitatory and inhibitory spiking neurons provide a parsimonious model of neural variability, but are notoriously unreliable for performing computations. We show that this difficulty is overcome by incorporating the well-documented dependence of connection probability on distance. Spatially extended spiking networks exhibit symmetry-breaking bifurcations and generate spatiotemporal patterns that can be trained to perform dynamical computations under a reservoir computing framework

* Comments and Summary (by David Hocker)

This paper was all about how thinking about the interplay of balanced state networks and consideration of spatial inhomogeneities in the model can give rise to meaningful and useful network behavior. The message was delivered pretty directly through PRL format, which can be difficult given the short amount of space in that kind of paper. The paper built upon previous work by Rosenbaum [here](https://journals.aps.org/prx/pdf/10.1103/PhysRevX.4.021039) that looked at mean-field solutions of networks that were allowed to have a spatial spread of probable connectivity, and how the spread of excitatory vs. inhibitory connections affected the overall “stability” of the balanced state. 
This paper took that same approach, but started to perform some additional analysis using linear response theory to understand the eigenvalue spectrum of the dynamics driving a perturbation to the network, something that their previous paper hadn’t done. Even in such a short paper there were quite a few results, but I’d say these are two of the important take-away points:

1. When inhibition is spatially broader than excitation, the typical form of stable balanced state dynamics goes away, and allows for Turing-Hopf bifurcations that can generate spatial patterning. This is shown Figure 1 of their paper, which was kind of a surprise to me and some of the other members of the group. I had always heard that it was strong inhibition that balanced these networks, so it was weird to see essentially “more” inhibition through larger spatial spread lead to something unstable (though arguably, as Giancarlo pointed out, this didn’t break the formal definition of the balanced state, just pushed it into a different regime). What you can see in the firing rates of c) and f) for these two network setups is that firing rates from random neurons have pretty much the same firing rate in the less-inhibitory-spread model, but wider variability in the larger-inhibitory-spread model. 
<p style = "text-align: center;">
<img src="/journalclub/images/rosenbaum_2017_fig1.PNG" width="400">
</p>
<p style = "text-align: center;">
Figure 1 from the paper
</p>

So what does that mean? What’s it good for? Well I think the main take-home message was in their final figure, which is …

2. Broader inhibitory spread and spatially inhomogeneous response to inputs can allow this network to actually do meaningful things like recreate a target sequence of activity, which would be necessary for this network to perform neural computations. Now the devil is in the details here, but the authors claim that if an input is given to the network in a homogenous manner (meaning all neurons receive input with the same weight), then it can’t do anything more than track the input signal. This means it can’t generate dynamics of it’s own based on that input to do computation. BUT, if this dependence upon the input were spatially varied, then the authors show that the network does a good job of generating arbitrary sequences using its internal dynamics. That’s what is shown in Figure 4 of their work:
<p style = "text-align: center;">
<img src="/journalclub/images/rosenbaum_2017_f4.PNG" width="400">
</p>
<p style = "text-align: center;">
Figure 4 from the paper
</p>

The PC projections show the first 5 principal components and how well they were recreated from trial to trial with a homogeneous (b) and heterogeneous (c) network. 

Overall the group seemed to like the paper. There were some comments and concerns about the sensitivity of the result to the enforced periodic boundary conditions, as well as the possible performance of a narrow-inhibitory-spread model to perform these sequence-generating tasks, but for the most part it looked pretty good. Solid journal club paper.