# 4. Finite Element Analysis of In-Place Behaviour of Masonry Shear Wall
For the course Computational Modelling of Structures (CIEM5210-1) I was tasked to investigate the in-plane behaviour of an unreinforced masonry wall using Finite Element Analysis (FEA). The study focused on a squat masonry wall (COMP-4) subjected to a horizontal loading and compared the numerical results to analytical and experimental results. This analysis was done to simulate the response of masonry to seismic loading. 

**Analysis Method**\
A finite element model was made first in DIANA, which can be seen in the figure below. Two models are made, on for smeared cracking (left) and one for discrete cracking (right). The elements of the wall are quadratic plane-stress sheet elements, meaning that each wall element has eight nodes and a 2x2 integration is used. Each wall node then has two degrees of freedom, $u_x$ and $u_y$. 

```{figure} ../../figures/MSc/CIEM5210-1_Models.png
---
width: 700px
align: center
---
Finite element model for smeared cracking (left) and discrete cracking (right)
```

In the experiment a steel beam was placed at the top, this steel beam was modelled as a quadratic class-III beam element, meaning that it has three degrees of freedom: $u_x$, $u_y$ and $\phi_z$. These elements have three nodes per element and have two integration points.

*Analyses*\
Three different analyses are done within this case study, which are: 

1. A nonlinear analysis with discrete cracking model and mean material properties. 
2. A nonlinear analysis with a rotating smeared cracking model and mean material properties. 
3. A nonlinear analysis with a rotating smeared cracking model and characteristic material properties. 

In each analysis, only physical nonlinearity is considered. This is because of the negligible effect geometrical nonlinearity adds to the model, due to the small deformations. For the discrete cracking analyses interface elements are embedded in the finite element model. Since the first and last layer of bricks is glued in reality, the cracks will happen in the masonry just above and below these layers.

*Incremental solution method*\
The iterative scheme that is used in all three analyses is full Newton-Raphson. In each analysis, twenty steps are taken for the prescribed displacement, and one step is taken for the pre-compression force. The maximum number of iterations per step was set to 100. The convergence criteria were both energy- and force norm of 0.0001 and 0.01 respectively was used with continuation after divergence.

**Numerical results**\ 
After setting up the finite element model, the three analyses were done. First the discrete cracking model analysis was done. The figure below shows the displaced structure at three different load levels. It shows that the discrete crack slowly opens.

```{figure} ../../figures/MSc/CIEM5210-1_DC_Results.png
---
width: 700px
align: center
---
Displaced discrete cracking model at three different steps
```

Then, the two smeared cracking model analyses were done. The figure below shows on the right the principal stresses, and on the left shows the development of the two diagonal crack bands in the masonry.

```{figure} ../../figures/MSc/CIEM5210-1_SC_Results.png
---
width: 700px
align: center
---
Displaced discrete cracking model at three different steps
```

*Comparison of all three analysis*\
The figure below shows the behaviour of all three analyses plus linear static analysis together with the experimental results, where SM_C is the smeared cracking model with characteristic properties, SC_M is smeared cracking with mean material properties, DC_M is discrete cracking with mean properties and LS is a linear static analysis.

```{figure} ../../figures/MSc/CIEM5210-1_Comparison.png
---
width: 700px
align: center
---
Displaced discrete cracking model at three different steps
```

**Conclusion**\
The discrete cracking model showed a significantly higher capacity compared to the experimental results. This is likely caused by a locking effect due to the placement of the interface elements. Placing these elements in a diagonal direction will likely reduce the locking effect and lower the capacity of the masonry wall, making the results more reliable.

Furthermore, the smeared cracking model analyses showed similar results. In these analyses two diagonal crack bands developed, which was more in line with reality compared to the discrete cracking model. All analyses overpredicted the capacity of the masonry wall. This is likely due to the simplification of the physical model in DIANA. The wall was modelled as a homogeneous plane stress element, while in reality, the masonry is highly inhomogeneous. To get more realistic results this inhomogeneity will need to be modelled. This can be done by modelling both bricks and mortar and giving different material properties. This shows that the case study required careful consideration and experience in the field of modelling problems where numerical results are only available.