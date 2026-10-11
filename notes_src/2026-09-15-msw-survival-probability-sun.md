---
title: "Why does P_ee(E) fall from 0.55 to 0.30? The adiabatic MSW formula in one page"
date: 2026-09-15
summary: "A short derivation of the adiabatic survival probability, with attention to where the theta13 factors enter."
tags: [MSW, oscillations, theory]
draft: false
---

Context from the [previous post](/notes/solar-neutrinos-2-5-mev-gap/): $P_{ee}$ goes from about 0.55 at low energy to about 0.30 at high energy, with the transition at a few MeV. The standard result for this is compact enough to derive in a few lines, and the derivation also shows what has to hold for it to be valid.

## Setup

In the effective two-flavour (1-2) problem, the matter potential $V_e=\sqrt2\,G_F n_e$ acts on $\nu_e$ only. Defining

$$\varepsilon \equiv \frac{2 V_e E \cos^2\theta_{13}}{\Delta m^2_{21}},$$

the matter mixing angle satisfies

$$\cos2\theta_m = \frac{\cos2\theta_{12}-\varepsilon}{\sqrt{(\cos2\theta_{12}-\varepsilon)^2+\sin^22\theta_{12}}}.$$

The factor $\cos^2\theta_{13}$ in $\varepsilon$ is the projection of the full charged-current potential onto the 1-2 subspace. It looks like a small correction, but it is important later, in the [post on a missing $\cos^2\theta_{13}$](/notes/two-bugs-in-one-hamiltonian/).

The resonance sits at $\varepsilon=\cos2\theta_{12}$. A neutrino produced where $\varepsilon\gg1$ starts as almost pure $\nu_{2}^m$.

## The adiabatic result

If the density changes slowly compared to the local oscillation length (the condition is made precise in [the adiabaticity post](/notes/adiabaticity-landau-zener/)), the neutrino stays in the matter eigenstate it started in. At the solar surface the matter eigenstates are the vacuum ones, and averaging out the unobservable Sun-Earth phase gives

$$P_{ee}^{2\nu}=\cos^2\theta_m\cos^2\theta_{12}+\sin^2\theta_m\sin^2\theta_{12}=\tfrac12\left(1+\cos2\theta_m\cos2\theta_{12}\right),$$

with $\theta_m$ evaluated at the production point. An equivalent form that makes the limits obvious is

$$P_{ee}^{2\nu}=\sin^2\theta_{12}+\cos2\theta_{12}\,\cos^2\theta_m .$$

Two limits:

- Vacuum-dominated ($\varepsilon\to0$, $\theta_m\to\theta_{12}$): $P_{ee}^{2\nu}=\tfrac12(1+\cos^22\theta_{12})\approx0.57$.
- Matter-dominated ($\varepsilon\to\infty$, $\cos^2\theta_m\to0$): $P_{ee}^{2\nu}=\sin^2\theta_{12}\approx0.31$.

Including the third mixing angle gives

$$P_{ee}=\cos^4\theta_{13}\,P_{ee}^{2\nu}+\sin^4\theta_{13},$$

which for $\sin^2\theta_{12}=0.31$ and $\sin^2\theta_{13}=0.022$ lands at about 0.55 and 0.30 in the two limits.

## Where the transition falls

With $\Delta m^2_{21}=7.5\times10^{-5}$ eV$^2$ and the electron density at $0.05\,R_\odot$ from the usual exponential profile $n_e\approx 245\,e^{-10.54\,r/R_\odot}$ mol cm$^{-3}$, the condition $\varepsilon=\cos2\theta_{12}$ gives $E\approx1.3$ MeV. The visible rise of $P_{ee}$ toward low energy is the stretch where $\varepsilon$ drops from large values to order one, a few MeV wide.

## What this formula leaves out

- A single production radius is assumed. The real production zone is extended ([a later post](/notes/where-8b-neutrinos-are-born/)).
- Non-adiabatic transitions are neglected.
- Earth regeneration at night is not included.
