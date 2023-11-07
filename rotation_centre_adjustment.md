# Rotation centre adjustment

## Introduction

The goal of this task is to  adjust the position of the centre of rotation of the suspension beams for a given position of the centre
of percussion. Namely, 

* **The centre of percusion** is at the lower side of the upper flexure, where the flexure couples with the marionete via
   the spring bldes, and
* **The centre of rotation** must be placed at the bottom inner face of the bottom alcove, where the beam couples with the
   mirror via the lower flexure.

This task will be accompished by judiciously varying the mass of the counterweight $m_{\rm cw}$, and calculating the *displacement* 
transfer function, defined as the ratio

$$ H = \frac{X_{\rm bottom}}{X_{\rm top}},$$

where $X_{\rm bottom}$ is the displacement of the he bottom inner face of the bottom alcove,
where we aim to place the centre of rotation, and $X_{\rm top}$ the the displacement of the centre of percussion. Both displacements
are the *longitudinal direction*.
The longitudinal direction is shown in the following diagram, which defines the standard coordinate system used for the mirror in GW detectors:

<img src="figures/standard_coordinate_system.png " alt="drawing" width="400"/>

We should avoid using the *xyz* naming convention because there's no agreement (among people and software packages) as to where those axes point to with respect to the mirror.

## Procedure

1. In COMSOL, consider a suspension beam, the upper flexure, the upper counterweight with $\rm m_{cw}$ and, the load with mass $\rm m_{load}$.
2. 
