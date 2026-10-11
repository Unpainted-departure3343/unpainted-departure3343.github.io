---
title: "How adiabatic is the Sun? Landau-Zener and a transfer-matrix check"
date: 2026-09-19
summary: "The adiabatic MSW formula assumes eigenstate labels are conserved. Two ways to check that assumption."
tags: [MSW, adiabaticity, numerics]
draft: false
---

The closed-form $P_{ee}$ from the [previous post](/notes/msw-survival-probability-sun/) rests on one assumption: the neutrino follows its local matter eigenstate all the way out. Near the resonance, where the eigenvalues approach each other, that assumption is exactly what can fail. So how big is the failure for solar neutrinos?

## The analytic estimate

At the resonance the adiabaticity parameter is

$$\gamma=\frac{\Delta m^2\sin^22\theta}{2E\cos2\theta\,\left|\partial\ln n_e/\partial r\right|_R},$$

and the Landau-Zener approximation for the probability of jumping between matter eigenstates is

$$P_{LZ}\approx e^{-\pi\gamma/2}.$$

For the exponential solar profile, $|\partial\ln n_e/\partial r|=10.54/R_\odot$, a scale of about $7\times10^4$ km. At $E=1.3$ MeV with LMA parameters, this gives $\gamma\sim10^{4}$, so $P_{LZ}$ is zero to any numerical precision. The 1-2 resonance in the Sun is about as adiabatic as a resonance can be.

For an extra level (a sterile state, say) the same estimate has to be redone at the new resonance, with the new $\Delta m^2$ and mixing angle. Nothing guarantees that the answer will be as comfortable.

## A numerical check that does not rely on the formula

The Landau-Zener expression is derived for a linear crossing, and the solar profile is exponential. An independent numerical test avoids that approximation:

1. At the production point, take each of the matter eigenstates $|\psi_i^{\rm prod}\rangle$ separately.
2. Evolve each one to the solar surface with the full Hamiltonian, using a direct integrator.
3. Project the result onto the surface matter eigenstates $|\psi_j^{\rm surf}\rangle$.

This builds a transition matrix

$$T_{ij}=\left|\langle\psi_j^{\rm surf}|U_{\rm evol}|\psi_i^{\rm prod}\rangle\right|^2 .$$

In the perfectly adiabatic limit $T$ is the identity, and every off-diagonal entry is a direct measure of non-adiabatic transition probability. The survival probability including non-adiabatic effects is then

$$P_{ee}=\cos^4\theta_{13}\sum_{ij}w_iT_{ij}\left|\langle\nu_e|\psi_j^{\rm surf}\rangle\right|^2+\sin^4\theta_{13},$$

where $w_i$ are the admixture weights of the initial $\nu_e$ on the production-point eigenstates.

## Um one imp note
The adiabatic and non-adiabatic branches must carry the same outer $\cos^4\theta_{13}$ and $\sin^4\theta_{13}$ projection. If one branch is projected and the other is not, the difference between them contains a constant offset unrelated to non-adiabaticity. This is a real pitfall, and one instance of it is described in the [post on cross-checks that disagree](/notes/when-the-cross-check-disagrees/).

