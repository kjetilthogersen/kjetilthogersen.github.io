---
layout: post
title: New paper on slip pulses
date: 2021-05-20 10:30:33 +0100
abstract: 'Check out our new paper in PRE!'
thumbnail: 'PRE-2021-slip-pulse.png'
---

Together with Einat Aharonov, Fabian Barras, and Fran&ccedil;ois Renard, I had a paper publishen in [Physical Review E](https://journals.aps.org/pre/abstract/10.1103/PhysRevE.103.052802) a few weeks ago.

### Background
The idea behind the paper was set up the simplest possible model that contains a transition from crack-like to pulse-like propagation of frictional rupture. In the end, we decided to go wit ha continuum version of the Burridge-Knopoff model with leaf springs. This continuum version on non-dimensional form contains only two parameters, an elasticity ratio, and the non-dimenionsional pre-stress (which is a function of space).

### Main results
* Slip pulses occur in a minimal continuum friction model with only two non-dimensional parameters. The transition from crack-like to pulse-like propagation as well as the pulse width scales with the system thickness, the rupture speed, the pre-stress and the elastic parameters of the material for displacement boundary conditions. For stress boundary conditions, the transition and the pulse width are entirely determined by the non-dimensional pre-stress.
* The onset of slip pulses can be explained by redistribution of elastic stress alone, which means that slip pulses are likely generic phenomena that exist for a wide range of friction constitutive laws.
* The stability of slip pulses is largely influenced by the system boundary conditions. Stress boundary conditions favor unstable slip pulses, while displacement boundary conditions favor stable slip pulses.

### Reproducing the results
Based on [this](https://github.com/kjetilthogersen/1D-rupture) GitHub repo, here is a simple notebook to reproduce the data in the figure above.

First import run_continuum from the repository
```python
import matplotlib.pyplot as plt
import numpy as np
import run_continuum as run

def gauss(x, mu, sigma):
    return np.exp(-(x - mu)**2/(2*sigma**2))
```

Then set up the prestress distribution $$ \bar \tau $$ and plot it
```python
# Set up and plot prestress distribution
x = np.linspace(0,50,1000)
tau = gauss(x,np.max(x)/2,1)*0.4 + 0.6
tau = tau/np.max(tau) # Make sure tau reaches 1, which is needed for triggering

plt.figure(figsize=(7,3))
plt.plot(x,tau)
plt.xlabel('$\\bar x$')
plt.ylabel('$\\bar \\tau$')
plt.show()
```



![png](/img/2021-05-25-new-paper-on-slip-pulses/output_1_0.png)



Then run the simulation with $$\bar \gamma = 0.65$$.
```python
# Run simulation with gamma = 0.65
data = run.run_continuum(x = x,
                         tau = tau,
                         tau_minus = tau+2,
                         dt = 1e-3,
                         output_interval = 100,
                         gamma = 0.65,
                         tmax = 15,
                         beta = 0.01)
```

This returns a dictionary with the output data. We can then recreate the left part of the figure in the paper:
```python
# Plot
plt.figure(figsize=(10,7))
plt.pcolor(data['t'],x,data['v'],shading='auto')
plt.xlabel('$\\bar t$')
plt.ylabel('$\\bar x$')
plt.title('$\\dot \\bar u, \\bar \gamma = 0.65$')
plt.colorbar()

plt.show()
```



![png](/img/2021-05-25-new-paper-on-slip-pulses/output_3_0.png)



The same thing can be done for a non-symmetric prestress distribution for $$\bar \gamma = 0$$.
```python
# Set up new prestress distribution that is not symmetric (and reaches 0):
x = np.linspace(0,50,1000)
tau = np.zeros(np.size(x))
tau[501:] = gauss(x[501:],np.max(x)/2,1)*1 + 0
tau[0:501] = gauss(x[0:501],np.max(x)/2,1)*1.5 - 0.5
tau = tau/np.max(tau) # Make sure tau reaches 1, which is needed for triggering

plt.figure(figsize=(7,3))
plt.plot(x,tau)
plt.xlabel('$\\bar x$')
plt.ylabel('$\\bar \\tau$')
plt.show()
```



![png](/img/2021-05-25-new-paper-on-slip-pulses/output_4_0.png)




```python
# Run the same simulation with gamma = 0
data = run.run_continuum(x = np.linspace(0,100,1000),
                         tau = tau,
                         tau_minus = tau+2,
                         dt = 1e-3,
                         output_interval = 100,
                         gamma = 0,
                         tmax = 50,
                         beta = 0.01)
```


```python
# Plot
plt.figure(figsize=(10,7))
plt.pcolor(data['t'],x,data['v'],shading='auto')
plt.xlabel('$\\bar t$')
plt.ylabel('$\\bar x$')
plt.title('$\\dot \\bar u, \\bar \gamma = 0$')
plt.colorbar()

plt.show()
```



![png](/img/2021-05-25-new-paper-on-slip-pulses/output_6_0.png)






### Open access
A version before copyediting (preprint) is available on [ArXiv](https://arxiv.org/abs/2012.11199). Check it out :smiley:
