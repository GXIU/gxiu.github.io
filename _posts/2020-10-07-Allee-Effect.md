---
title: Allee Effects, Phase transitions in epidemic spreading on meta-population structures
date: 2020-10-07
description: Why community-wide quarantine is not a 100 % good policy for COVID-19?
categories:
  - health
  - research
image: https://www.researchgate.net/profile/Xavier_Fauvergue/publication/305716419/figure/fig1/AS:389237858947076@1469812945304/Extinction-vortices-driven-by-Allee-effects-In-ecological-Allee-effects-a-decrease-in.png
author_staff_member: George

---

Community-wide quarantine may create a denser local population structure, and may increase the $R_0$ value of the epidemic.

<!-- ![Man](https://source.unsplash.com/random/1500x1000) -->

## How is the population structured, and how does quarantine work

### Epidemic model in spatially structured meta-population

### Epidemic model for purpose-driven visit among meta-population

## Invasion threshold in spatial structured populations

<!-- ![Thai](https://source.unsplash.com/random/1500x1001) -->

To find the transition point in the quarantined population framework, we adopt a branching process procedure to describe the epidemic spread across meta-populations. Let us consider a city with $M$ meta-populations, the distribution of population size of each subpopulation is $p_k$ for $k = 1,2,3,\dots$. Within each subpopulation, we assume that the people interact with the rate proportional to its population and statistically equivalent and uncorrelated. Let $J_n$ be the number of newly-become infected communities at iteration $n$, obtaining that

$$
J_n = J_{n-1} \left( 1 - \frac{\sum_{m = 0}^{n-1} J_m}{M} \right) C \Phi,

$$

where $C$ is the average neighbor of a meta-population, $\Phi$ is the probability of infection, and thus $( 1 - \frac{\sum_{m = 0}^{n-1} J_m}{M} )C$ is the average uninfected neighbors. So that the global contagion condition is that $J_n / J_{n+1} \geq 1$.

- When interested in the early process of the model, the term $ \frac{\sum_{m = 0}^{n-1}J_m}{M}\approx 0$, thus $ R_0^* = C\Phi$.

If we denote $ \langle k \rangle $ as  the average degree of the meta-population network, then $ C = \langle k\rangle - 1$. If $ \beta$ is the number of spreaders in an affected meta-population that can travel outside of the meta-population, and $f$ as the mobility parameter, then the probability of the spread towards none of the neighbors is

$$
1 - \left( 1 - \frac{f}{\langle k\rangle} \right) := \Phi.

$$
