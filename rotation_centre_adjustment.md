# Rotation centre adjustment

## Introduction

The goal of this task is to  adjust the position of the centre of rotation of the suspension beams for a given position of the centre
of percussion. Namely, 

* **The centre of percusion** is at the lower side of the upper flexure, where the flexure couples with the marionete via
   the spring bldes, and
* **The centre of rotation** must be placed at the bottom inner face of the bottom alcove, where the beam couples with the
   mirror via the lower flexure.

Let us call these geometrical places **top** and **bottom** points respectively.

This task will be accompished by judiciously varying the mass of the counterweight $m_{\rm cw}$, and calculating the *displacement* 
transfer function, defined as the ratio

$$ H = \frac{X_{\rm bottom}}{X_{\rm top}},$$

where $X_{\rm bottom}$ is the displacement of the bottom point and $X_{\rm top}$ the the displacement of the top one. Both displacements
are in the *longitudinal direction*.
The longitudinal direction is shown in the following diagram, which defines the standard coordinate system used for the mirror in GW detectors:

<img src="figures/standard_coordinate_system.png " alt="drawing" width="400"/>

We should avoid using the *xyz* naming convention because there's no agreement (among people and software packages) as to where those axes point to with respect to the mirror.

## Procedure

1. In COMSOL, consider a suspension beam, the upper flexure, the crossbeam, the upper counterweight with mass $m_{\rm cw}$, and a load with mass $m_{\rm load}$.
   1. Initially, the top point must be fully constrained in all six degrees of freedom.
   2. To begin with, set the value of the counterweight mass $m_{\rm cw}$ equal to 0.809 kg (per [Fabián's report](reports/cryogenic_suspension_rigid_body_model_fabian.pdf)).
   3. The load must be placed at the bottom point and its mass $m_{\rm load}$ must be equal to one-quater of the mass of the mirror, namely, 50 kg.
   4. All the other components must be at their nominal places with their nominal physical properties.

2. By means of a modal analysis, identify the resonant frequency $f_{0}$ in which the suspension beam behaves nearly as rigid body, and where flexure deforms a lot. In Fabian's report on the rigid body simulation, this frequency was arbitrarily chosen to be 16.65 Hz. See this transfer function:
   <img src="figures/transfer_function_amplitude.png" alt="drawing" width="400"/>
4. Tell Fabián the result so he can use the rigid body simulation to calculate the frequency $f_{\rm sat}$ in which the effect of the misplacement of the centre of rotation is expected dominate. The subindex in $f_{\rm sat}$ stands for saturation.

5. Release the contraint imposed to the top point in the longitudinal direction only, and keep the other five constraints.
  
2. At a frequency larger than $f_{\rm sat}$, set the top point to move sinusoidally in longitudinal with an amplitude of your choosing,   say, 200 $\rm \mu m$.

3. Use COMSOL to calculate the amplitude of the motion of the bottom point.
4. Calculate the *amplitude* of the transfer function defined above. How large is this value? It is expected to be small, like between $10^{-4}$ and $10^{-6}$.
5. Check whether the top and bottom points are on the same side of the equilibrium position when they move. In such a case, the centre of rotation is below the bottom point, and **increasing** $m_{\rm cw}$ would **move it up**.
6. In case the points are on opposite sides of the equilibrium position as they move, the centre of rotation is above the bottom point, and **decresing** $m_{\rm cw}$ would **move it down**.
7. Because the goal is to set the centre of rotation as close as possible to the bottom point, it's necesssary to repeat the steps above after adjusting the counterweight mass $m_{\rm cw}$ either up and down, and  by smaller amounts each repetition. First, use steps of 10 g, then several or a few grams, a gram, and finally 0.1 g.
8. Calculate the transfer function for several frequencies above the one you were working at, and check whether the plot looks like a plateau or just decreases with frequency.
9. If possible, calculate the transfer function in all frequencies of interest. I'm not sure if COMSOL would be able to do this easily.
