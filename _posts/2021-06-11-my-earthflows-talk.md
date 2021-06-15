---
layout: presentation
title: My EarthFlows Talk
date: 2021-06-11 09:00:00 +0100
abstract: 'Last week we had a two-day seminar with EarthFlows at NJORD/UiO with both internal and invited speakers. My talk was about a paper that is currently under review. Here it is, with a few modifications to adapt it to a written format.'
tags: glaciology surge glacier seminar talk presentation
thumbnail_link: 'https://www.mn.uio.no/geo/english/research/groups/earthflows/bilder/earth-flows-180px.png'
item: 1
auto: false
loop: false
speed: 1000
pause: 4000
pager: "true"
controls: "true"
adaptiveHeight: "true"
---

The preprint which this talk builds on can be found [here](https://doi.org/10.31223/X5JG87). Links to papers by other groups where I show some results for context are given in each individual slide. Simulations are done using [pyGlacier](https://github.com/kjetilthogersen/pyglacier) (which I will probably write a bit about later).

1. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.001.jpeg)
My talk was about modeling glacier velocity variations, and in particular the importance of the physics at the base of glaciers. Glaciers move through a combination of viscous creep and sliding over it's base. In order to capture the wide variety of glacier motion that we observe in nature, we need to capture the essential processes a t the glacier bed, which include both sliding friction and subglacial drainage.

3. <iframe width="460" height="250" src="https://www.youtube-nocookie.com/embed/E4Zc_KuXMkA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
Before I explain what we have done, let’s have a closer look at the satellite images that you see in the background. In the talk (which was limited to 20 minutes), I showed a few examples from the embedded youtube video, but I really recommend watching the entire video. It shows yearly images of several glaciers in Alaska from the seventies until now. The satellite images were put together by Mark Fahnestock from the University of Alaska, Fairbanks. The video contains an interview of him where he explains what you see. What I would like to highlight is the large variety of motion that is observed. In this presentation I will focus on the pulsating velocities called glacier surges you see for the Logan/Walsh and Klutlan glaciers. These glaciers increase their speed by orders of magnitude for a short period of time in between longer periods of low velocities.

4. <iframe width="460" height="250" src="https://www.youtube-nocookie.com/embed/-lUOIyBfQlI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
The next video to show is from the Klutlan glacier, and was put together by Bas Altena. It shows a closer look at what happens during a surge event. The dots you see are tracers that follow the velocity field of the glacier which has been found from satellite images. What you can see it that the surge nucleates in a region around the central part of the glacier, and then propagates both down glacier (to the right), but also up-glacier.

6. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.006.jpeg)
This is perhaps more evident if we look at the velocity maps with time going from left to right. The colors show glacier surface speed measured in meters per day (which is quite fast for a glacier). You see nucleation in the central part of the glacier, and the region of high velocity expands in both directions. You can find the paper by Altena on how these velocity maps are created [here](https://doi.org/10.5194/tc-13-795-2019).

7. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.007.jpeg)
Taking the centerline velocities, you get the spatiotemporal evolution in a single plot. Here you have time on the y-axis (from top to bottom) and position along the centerline on the x-axis. Again, the colors show surface velocities in meters per day. This is a way of visualizing the data that clearly shows the evolution of the surge front. From the solid and dashed lines, it is then possible to extract the propagation speed; that is the speed at which the high velocity region grows in space.

7. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.008.jpeg)
Let’s go back to how glaciers move for a moment. They move through a combination of viscous deformation (at large time-scales well described by the Stokes equations with non-linear viscosity). This is quite well understood. The velocity increase, and also the propagating front, occurs through changes in basal friction. The figure in this slide is taken from a paper we had published in Nature Communications in 2019, which you can find [here](https://doi.org/10.1038/s41467-019-10506-4).

8. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.009.jpeg)
The figure that popped up here shows a friction constant beta, found from inverting surface velocities from the Variegated glacier, Alaska, just before and during a surge event (paper where they explain what they did can be found [here](https://doi.org/10.5194/tc-5-659-2011)). The assumption at the base is a linear velocity strengthening law. You can see that basal friction is significantly lowered, and you can also see the down-glacier propagation to the right of this zone of low friction.

9. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.010.jpeg)
Since this instability clearly depends on capturing changes in basal friction, let me give a very short, and for that reason highly selective, literature review of advances in the last few years. The temperature conditions at the base of glaciers varies, and we usually separate glaciers in cold based, polythermal, and temperate.
I’ll only cover temperate glaciers, where ice is at the pressure melting point. This means I will not talk about temperature effects.

10. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.011.jpeg)
The base of glaciers contains two end-members. Let's start with the first one, hard-bedded glaciers, where ice is sliding over rigid bedrock. Friction laws have for this case have been developed based on numerical simulations, with the assumption that the main contribution to sliding resistance is that ice has to flow around obstacles at the bed. Due to lower pressures at lee side of obstacles, you will develop cavities that grow with increasing velocity. The 2D sketch of this is shown in the top left figure, which is taken from a study by Schoof (which can be found [here](https://doi.org/10.1098/rspa.2004.1350)).
The large image shows a very recent study by Helanow et. al (which can be found [here](https://doi.org/10.1126/sciadv.abe7798)), where they used measured bedrock topographies. This is possible because retreating glaciers reveal the topography so that it can be measured with high precision. The colors scale shows cavity height, and as you increase the speed ...

11. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.012.jpeg)
these cavities start to grow

12. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.013.jpeg)
...

13. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.014.jpeg)
...

14. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.015.jpeg)
From these simulations, it is possible to extract the shear stress as a function of sliding velocity, and you see some of the results of this study on the left.
For these topographies they find that the basal shear stress increases with velocity, and reaches a plateau.  The same type of study has been done in 2D, which highlighted the possiblity of a transition to velocity weakening friction at large sliding speeds. The Gagliardini study (found [here](https://doi.org/10.1029/2006JF000576)) is numerical, while the study by Zoet (found [here](https://doi.org/10.3189/2015JoG14J174)) is Experimental. Largely based on the study by Helanow et. al, the role of velocity weakening friction for hard-bedded glaciers is under debate. A few weeks back, Neal Iverson took part in this study, had a really interesting talk over zoom at the NJORD seminar series. His talk was recorded, and can be found [here](https://www.mn.uio.no/njord/bilder/njord-seminar-series/neal_iverson.mp4). If you are interested in this topic, check it out! Nevertheless, I will use the assumption of velocity weakening friction in simulations I will show soon.

15. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.016.jpeg)
The other end-member of glacier beds is soft-bedded glaciers, where ice is sliding over deformable sediments (tills).
What is very interesting, is that ice sliding over subglacial till, Iverson and Zoet find a very similar behavior (Their study in science can be found [here](https://doi.org/10.1126/science.aaz1183)). They find that till resistance is constant at high velocities. This actually fits very well with the same functional form of shear stress vs. sliding speed that they find for hard-bedded glaciers (in the Helanow study), which is velocity strengthening at low velocities and then saturates at a close to constant value. They actually state this directly in their paper:
«These results motivate a generalized slip law for glacier-flow models that combines processes of hard-bedded sliding and bed deformation.»

16. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.017.jpeg)
It's basically impossible to talk about friction without at some point reaching rate-and-state friction. The list of studies using this law is almost endless, and it has been very popular in earthquake, landslide and tribology communities. I mention it here because it has also been applied as a constitutive law at the base of glaciers, in combination with a separate evolution law for till porosity (see for example [this](https://doi.org/10.1098/rspa.2020.0033) study). Rate-and-state friction states that friction is not only velocity dependent (rate), but also depends on the state of the interface (for example porosity or real area of contact). In steady state, these equations return a logarithmic velocity dependence that is either strengthening or weakening depending on the choice of parameters a and b.

17. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.018.jpeg)
We can summarize this in the figure on the right. The red curve shows the generalized Coulomb law (which is what they call the parameterization in the studies by Helanow and Zoet), which can be assumed to have the same functional form for both soft-bedded hand hard-bedded glaciers. The blue curve shows a variant of this that was introduced from 2D simulations of hard-bedded glaciers. This one is identical to the generalized Coulomb law if the parameter q is set to 1. If q is larger, there is a transition from velocity strengthening to weakening at higher speeds. This is the parameterization I will use in the simulations I show you soon. The yellow curve shows the steady state friction for classical rate and state. Since we use log-axes, this produces a straight line in the figure. As a note, it is possible to view rate-and-state as a linearization of the high velocity regime of the blue curve.

18. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.019.jpeg)
Now let's turn from the literature review to what I have actually done. We will start with formulating a rate-and-state type parameterization that couples friction (based on the studies I showed you in the previous slide) to subglacial drainage.

19. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.020.jpeg)
I will make two assumptions. The first one is not really an assumption at all: friction is transient. For friction laws used in earthquakes for example, this has been known for a very long time, but the same type of effect applies to subglacial cavities, but with transients occuring over longer time-scales. The figures show some results from a study by Zoet (can be found [here](https://doi.org/10.3189/2015JoG14J174) for ice sliding over sinusoidal bedrock, for a step change in driving speed, the shear stress first increases (called the direct effect), and then slowly evolves towards a new steady state over several days.


21. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.022.jpeg)
The second assumption is more empirical of nature: The state of the interface (which we introduce in the equations on the next slide) represents either porosity or degree of subglacial cavitation. The hydraulic conductivity (that is how quickly water can be drained from the base) should depend directly on the state as illustrated here. When cavity extent and height increases, the conductivity increases, with a possible additional complexity of a subglacial percolation criterion where cavities start to form a connected network.

22. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.023.jpeg)
Based on this, we can parameterize the basal response through these 3 equations. First, the state evolution law.
* The state of the interface, $$ \theta $$, evolves towards a steady state encoded in $$ \theta^\dagger $$, through creep (with timescale $$ t_c $$) and sliding (with length scale $$ d_c $$). $$ \theta^\dagger $$, is set so that the steady state solution equals the Gagliardini parameterization (which was given a few slides back).
* The basal shear stress, $$ \tau_b $$, can then be found from the current sliding speed, $$ v $$, and the current state of the interface. with some additional rheology constants $$ A_s $$ and $$ n $$
* The hydraulic conductivity $$ K $$ is set by a background level $$ K_0$$, and a term that depends on the state of the interface.

23. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.024.jpeg)
This is how it works for step changes in sliding velocity (which is what is often done in experiments). The middle and right panels show steady state friction and conductivity as a function of sliding speed. For step changes in velocity given from the top left panel, we recover the direct effect and a transient evolution towards a new steady state. In addition, we introduce a transient in the hydraulic conductivity through the transient changes in porosity/cavitation (bottom left).
You should note that there are several aspects of this parameterization where we need more data and experiments to be certain about the functional form. One important part is the response to changes in normal stress, which is very relevant if water pressure is changing at the glacier bed, but where experimental data is limited.

24. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.025.jpeg)
Now let's have a look at some simulation results incorporating the parameterization introduced here.

25. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.026.jpeg)
In a presentation like this, it is a bit too much to cover the entire set of equations we solve, but this sketch summarizes it. We solve for ice deformation with an altitude dependent source term for the surface mass balance. At the base,  we supply a water source term which enters a drainage system with two components. The first is a distributed system that is more or less captured by the equations in the previous slide. The second part is a low pressure conduit system, where conduits open by melting and close by viscous creep. Both systems have efficient and non-efficient modes. The distributed system can increase its hydraulic conductivity through increasing sliding speed. The conduit system is more efficient when the glacier is thin because the conduits open more readily.

26. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.027.jpeg)
If you are interested in the details, you can check out the preprint found [here](https://doi.org/10.31223/X5JG87), or the [pyGlacier](https://github.com/kjetilthogersen/pyglacier) repo that I will probably write more about later (documentation is currently limited to a few notebooks with examples).

27. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.028.jpeg)
We can start with what keeps glacier stable. There are a number of things that can keep a glacier stable (that is non-surge type). The minimum criterion as that changes in surface slope caused by surface mass balance does not trigger a frictional instability at low water pressure. Then, if the water pressure is kept low enough, the glacier will not surge. This can be done through:
* Efficient conduits. This means steep and thin glaciers are less likely to surge (shown in B).
* If the hydraulic conductivity of the bedrock is large, so that all incoming water is immediately drained.
* The change in conductivity with increasing sliding speed is large, and occurs without surpassing a frictional stability criterion. If this is the case, the glacier can still exhibit quite strong velocity fluctuations, but will not be unstable in the sense of crack-like propagation of a surge region.

29. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.030.jpeg)
Let us have look at a glacier surge in the model. The glacier geometry is shown on the top. The middle panel shows velocity, and the bottom panel shows effective normal stress in blue, basal shear stress in orange, and stress from glacier margins in green. The video plays in the next slide.

25. <video width="460" height="250" controls> <source src="/img/2021-06-11-my-earthflows-talk/surge_simulation.mp4" type="video/mp4"> </video>
The instant where the video starts is just prior to a surge, where the water pressure is fairly high in the central part of the glacier (low effective normal stress). Then you have a surge propagating down glacier with low values of basal shear stress. When the surge reaches the front, water drains and the effective normal stress increases. In the process, the glacier geometry has changed because of the propagating surge front. The glacier has thinned and is slightly longer.
* If the movie doesn't play (I'm too lazy to make this work for all browsers), you can download from a direct link [here](/img/2021-06-11-my-earthflows-talk/surge_simulation.mp4).

30. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.031.jpeg)
From a surge event we can produce a spatiotemporal velocity map as this one (which is equivalent to Bas made from satellite images as I showed in the first few slides of the talk). There is a clear nucleation region in the central part of the glacier, and in this case mainly donwglacier propagation (up in the plot) of the surge. I would like to point out a few observations about the role of velocity weakening friction, since this is an ongoing discussion in the literature. Velocity variations themselves do not necessarily require velocity weakening, but the observed behavior is quite different from what you see here which assumes velocity weakening. From the simulations, well defined nucleation and sharp surge fronts seem to require velocity weakening friction.

31. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.032.jpeg)
The plot in the previous slide is part of a larger simulation, which I will walk you through in the next few slides. Let’s first look at is the state of the interface during the surge. Remember that this gives the prefactor to the velocity-dependence of basal shear stress as well as the hydraulic conductivity. What this shows you is that basal friction is low and hydraulic conductivity is high in the region affected by the surge.

32. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.033.jpeg)
Here I have added a time series of the spatially averaged glacier velocity, where you can see a number of velocity increasing events. The background colors in the panels correspond, and the surge on the right can be seen as a tiny pink line in the time-series. This example also illustrates that the surge interval is not necessarily constant, and that there can be a large variety of events for the same glacier. The events with smaller magnitude do not affect the entire glacier, and at least from the surge definition I adopt in the preprint they are not considered surges (a robust definition of glacier surges is surprisingly difficult to come up with).

33. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.034.jpeg)
The average effective normal stress shows some of what is going on. Prior to surges, there is a slow decay of effective normal stress. Due to the applied surface mass balance term the average thickness increases in this period, which means that the reason for the decaying effective normal stress is an increasing water pressure. During surge events, the water pressure decreases (effective normal stress decreases). A surge event is in that respect a drainage event of the distributed drainage system, but for it to act as an instability, velocity weakening friction is needed.

34. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.035.jpeg)
If we then have a closer look at the buildup of a surge, we find three phases.
- I: The effective normal stress is constant
- II: The ffective normal stress decreases gradually
- III: The effective normal stress increases again after a surge because the water pressure is lowered.

35. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.036.jpeg)
These stages can be understood from the water exchange between the conduit system and the distributed system. In the first stage, most entering the system is drained through conduits, but as the glacier thickens, the conduits are eventually unable to drain all the water. The red line shows the averaged water input, while the blue line shows the exchange term from the distributed system to the conduit system. This means water pressure will slowly build if the distributed system is not efficient enough.

36. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.037.jpeg)
Then, the water pressure increases gradually until an instability is triggered in the central part of the glacier. This can be seen from the spatiptemporal effetive normal stress, which decreases in the central part of the glacier.

37. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.038.jpeg)
To complete the figure, we can have a look at the changes in ice thickness. In the period between surges, the glacier shortens and steepens. During a surge, the increased sliding speeds flushes ice down glacier, elongating and thinning the glacier.

38. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.039.jpeg)
This was only one of many simulations, and there is a rich variety of behaviors I didn’t really have time to cover, but check out the preprint.
The simulations show that the coupling between friction and drainage is sufficient to reproduce a large range of velocity variations and surge characteristics.

39. ![Slide](/img/2021-06-11-my-earthflows-talk/EarthFlows2021_img.040.jpeg)
But, the model contains a number of empirical parameters. For it to be useful, we need validation. Through the MAMMAMIA project, data will be gathered from the Kongsvegen glacier in Svalbard, which we believe is on the verge of surging. This is what the next talk is about.
