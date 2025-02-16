# 3. Dynamic Analysis around the static equilibrium of a bridge
As a second assignment for the course Slender Structures (CIEM5000) we were tasked to analyse the dynamic response of a bridge around the static (assumed known) equilibrium of the system due to the own weight of the structure. The model of the bridge that was analysed is depicted below.

```{figure} ../../figures/MSc/CIEM5000_A2_Bridge.png
---
width: 600px
align: center
---
Model of bridge to be analysed
```

The structure was dynamically excited by a distributed vehicle load, and a vertical seismic motion (as shown in the figure). 

The first step was to formulate the governing equations of this system, i.e. the equations of motion, boundary conditions and the interface conditions. Furthermore, we assumed that the structure was initially at rest. I split up the structure into several pieces, each defined by its own EoM and subject to boundary and interface conditions.

**Modal shapes and natural frequencies**\
The next step in the analysis was to derive the natural frequencies and the modes of vibration of the structure. This was done by using the following steps:

1. Remove all external forces from the EoMs of the system and dropping time-dependence from all governing equations by introducing frequency (omega) as a running parameter.
2. Formulate the algebraic matrix equation. Setting the determinant of the matrix to zero provides the eigenfrequencies (natural frequencies).
3. Derive the eigenmodes (natural modes of vibration) and normalising those.
4. Use the orthogonality condition to transform the forced equations of motion into a set of uncoupled ODE’s in the modal domain.
5. Derive the response to each modal coordinate.
6. Retrieve the response in the actual space-time domain by summing over the modal contributions.

This method resulted in the modal shapes of the structure. The first six modes as displayed in the figure below:

```{figure} ../../figures/MSc/CIEM5000_A2_Modal_Shapes.png
---
width: 700px
align: center
---
First six modal shapes of the bridge
```

**Steady-state response**\
The next step was to compute the steady-state response of the structure subjected to both vehicle and seismic loads. This was done using the dynamic stiffness matrix method (DSM). Since the structure is subject to two different types of loads with different frequencies, two different steady-state responses need to be analysed. Since the system is linear both of these responses can be added to get the full response of the structure. The total real part of the bending moments of the bridge deck for the steady-state response are given below.

```{figure} ../../figures/MSc/CIEM5000_A2_SSR.png
---
width: 500px
align: center
---
Steady-state response of the bridge deck
```

**Time domain response**\
The last step of this analysis included the computation of the time domain response of the structure subjected to both vehicle and seismic loads and finding the position and value of the maximum stress in the pylon. To obtain the time domain response the Fourier transform is used. First, the orthogonality relation is used to calculate the complex modal amplitudes per frequency. These amplitudes are then used to calculate the response per frequency by matrix multiplication with the normalised modes. Then the time domain response is computed by taking the inverse Fourier transform of the frequency domain. The time domain responses are the excitations in the longitudinal and transversal direction of the pylon. The moment and normal forces are then obtained by numerical differentiation of the time domain responses multiplying with $-EI_p$ and $EA_p$ respectively. The stresses are then computed by using the following two formulas:

$$\sigma = \frac{M \cdot z}{I} \quad \mathrm{and} \quad \sigma = \frac{N}{A}$$

This results in the bending and normal stresses at each point in the pylon throughout time. Please note that the force is assumed to be harmonic. Taking the maximum value at each point will result in the following plot:

```{figure} ../../figures/MSc/CIEM5000_A2_TDR.png
---
width: 500px
align: center
---
Maximum stress in the pylon
```

This extensive and complex assignment showed me how an in-depth analysis can be done on civil structures subject to all kinds of dynamic loading.