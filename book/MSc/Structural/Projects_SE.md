# Projects
This page contains the projects I did during my master's degree Structural Engineering at the Technical University Delft.

## Mathematical Optimization of Zandhazenbrug
For the course Programme Base (CIEM0000) of the master Structural Engineering, I was part of a team of four students, and we were tasked to optimise a project based on mathematical models considering several stakeholders, objectives, and constraints. We chose to optimise the Zandhazenbrug near Muiderberg. 

**Stakeholder analysis**\
Firstly, a stakeholder analysis is done to map the stakeholders in a power-interest grid and gather all the requirements. These requirements where then used to set up several criteria for the multi-criteria decision analysis.

**Multi-Criteria Decision Analysis (MCDA)**\
The project started with doing a multi-criteria decision analysis to analyse three alternative solutions. The three design alternatives that were considered were:

1. Bridge without a center pillar
2. Tunnel under the highway
3. Bridge with a center pillar

From the MCDA software the original design (Bridge without centre pillar) emerged as the best option due to minimal disruption and optimal cost-effectiveness. Since we got the best design, we can optimize it using mathematical models.

**Design optimization**\
First, the design variables are determined. The first variable is the bridge span (x1) and the second variable is the bridge width (x2). The bridge span directly influences the traffic flow capacity of the highway underneath the bridge, while the bridge width influences the train frequency. Both the variables influence the material use, which in turn influence the cost and $CO_2$ emissions. The problem statement is depicted in the figure {ref}'problem-statement' test.

```{figure} ../../figures/MSc/CIEM0000_Flowchart.jpg
---
width: 500px
align: center
name: problem-statement
---
Problem statement visualisation
```

The next step was to create linear objective functions that rate the performance of a design and constraints. This resulted in a solution space which is depicted in the figure below.

```{figure} ../../figures/MSc/CIEM0000_Solution_Space.jpg
---
width: 350px
align: center
---
Solution space
```

The last step of the optimization was to perform a Multi-Objective Design Optimization (MODO). The IMAP and MINMAX algorithms were used to find the optimal design that balances stakeholders needs. The result of the algorithms is shown in the figure below. 

```{figure} ../../figures/MSc/CIEM0000_Optimal_Solution.jpg
---
width: 500px
align: center
---
Optimal design solution using both algorithms
```

After running the MCDA for both design solutions, it turns out that the MINMAX solution was the best solution with a span of 276.1 m and a width of 10.6 m. 

During this project I learned that everyday decisions can be optimized using mathematical models and that it is very important to listen to stakeholder requirements.

## Coding the Matrix Method in Python
The matrix method is a widely used method to determine forces, displacements, and stresses in engineering structures and is the basis for computational analysis. It is widely applied in analysing beams, trusses, and frames by representing the system as a set of linear equations. As part of the course Slender Structures (CIEM5000) I was tasked to write the matrix method in Python and apply it to a complex structure.

**Writing code**\
A big part of the assignment was to write the code of the matrix method in Python. We were given the beginning of a code, but our task was to finish it and include a different type of loading (a distributed sine load) to analyse the structure given below.

```{figure} ../../figures/MSc/CIEM5000_MM_Structure.jpg
---
width: 500px
align: center
---
Structure that is analysed using the Matrix Method
```

Object Orientated Programming was used to write the code and make it easily applicable to a lot of structures. The code can be divided into three separate parts:

1. Node class
2. Element class
3. Constrainer class

The **Node class** was used to store node information and keep track of the total number of Degrees of Freedom (DOFs) of the problem. 

The **Element class** kept track of each element in the model, including cross-section properties, element orientation, and the nodes that make up each element. The element class was responsible for providing the element stiffness matrix in the global coordinate system  and postprocessing element-level fields. The class described an element combining extension and Euler-Bernoulli or Timoshenko bending and can output displacements and bending moments.

At last, the **Constrainer class** represents a constrainer for fixing degrees of freedom in a structural analysis. This class is able to fix a DOF of a node, fix the displacement of a node, and output the support reaction forces of the model.

**Result**\
The result of the report was the fully displaced structure, moment line of the structures, and support reactions.

```{figure} ../../figures/MSc/CIEM5000_MM_Result.jpg
---
width: 700px
align: center
---
Result of the Matrix Method analysis
```

## Dynamic Analysis around the static equilibrium of a bridge
As a second assignment for the course Slender Structures (CIEM5000) we were tasked to analyse the dynamic response of a bridge around the static (assumed known) equilibrium of the system due to the own weight of the structure. The model of the bridge that was analysed is depicted below.

```{figure} ../../figures/MSc/CIEM5000_A2_Bridge.jpg
---
width: 400px
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

```{figure} ../../figures/MSc/CIEM5000_A2_Modal_Shapes.jpg
---
width: 700px
align: center
---
First six modal shapes of the bridge
```

**Steady-state response**\
The next step was to compute the steady-state response of the structure subjected to both vehicle and seismic loads. This was done using the dynamic stiffness matrix method (DSM). Since the structure is subject to two different types of loads with both different frequencies, two different steady-state responses need to be analysed. Since the system is linear both of these responses can be added to get the full response of the structure. The total real part of the bending moments of the bridge deck for the steady-state response are given below.

```{figure} ../../figures/MSc/CIEM5000_A2_SSR.jpg
---
width: 350px
align: center
---
Steady-state response of the bridge deck
```

**Time domain response**\
The last step of this analysis included the computation of the time domain response of the structure subjected to both vehicle and seismic loads and finding the position and value of the maximum stress in the pylon. To obtain the time domain response the Fourier transform is used. First the orthogonality relation is used to calculate the complex modal amplitudes per frequency. These amplitudes are then used to calculate the response per frequency by matrix multiplication with the normalised modes. Then the time domain response is computed by taking the inverse Fourier transform of the frequency domain. The time domain responses are the excitations in longitudinal and transversal direction of the pylon. The moment and normal forces are then obtained by numerical differentiation of the time domain responses multiplying with $-EI_p$ and $EA_p$ respectively. The stresses are then computed by using the following two formulas:

$$\sigma = \frac{M \cdot z}{I} \quad \mathrm{and} \quad \sigma = \frac{N}{A}$$

This results in the bending and normal stresses at each point in the pylon throughout time. Please note that the force is assumed to be harmonic. Taking the maximum value at each point will result in the following plot:

```{figure} ../../figures/MSc/CIEM5000_A2_TDR.jpg
---
width: 350px
align: center
---
Maximum stress in the pylon
```

This extensive and complex assignment showed me how an in-depth analysis can be done on civil structures subject to all kinds of dynamic loading.

## Finite Element Analysis of In-Place Behaviour of Masonry Shear Wall
For the course Computational Modelling of Structures (CIEM5210-1) I was tasked to investigate the in-plane behaviour of an unreinforced masonry wall using Finite Element Analysis (FEA). The study focused on a squat masonry wall (COMP-4) subjected to a horizontal loading and compared the numerical results to analytical and experimental results. This analysis was done to simulate the response of masonry to seismic loading. 

**Analysis Method**\
A finite element model was made first in DIANA, which can be seen in the figure below. Two models are made, on for smeared cracking (left) and one for discrete cracking (right). The elements of the wall are quadratic plane-stress sheet elements, meaning that each wall element has eight nodes and a 2x2 integration is used. Each wall node then has two degrees of freedom, $u_x$ and $u_y$. 

```{figure} ../../figures/MSc/CIEM5210-1_Models.jpg
---
width: 500px
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

```{figure} ../../figures/MSc/CIEM5210-1_DC_Results.jpg
---
width: 600px
align: center
---
Displaced discrete cracking model at three different steps
```

Then, the two smeared cracking model analyses were done. The figure below shows on the right the principal stresses, and on the left shows the development of the two diagonal crack bands in the masonry.

```{figure} ../../figures/MSc/CIEM5210-1_SC_Results.jpg
---
width: 600px
align: center
---
Displaced discrete cracking model at three different steps
```

*Comparison of all three analysis*\
The figure below shows the behaviour of all three analyses plus linear static analysis together with the experimental results, where SM_C is the smeared cracking model with characteristic properties, SC_M is smeared cracking with mean material properties, DC_M is discrete cracking with mean properties and LS is a linear static analysis.

```{figure} ../../figures/MSc/CIEM5210-1_Comparison_Results.jpg
---
width: 500px
align: center
---
Displaced discrete cracking model at three different steps
```

**Conclusion**\
The discrete cracking model showed a significantly higher capacity compared to the experimental results. This is likely caused by a locking effect due to the placement of the interface elements. Placing these elements in a diagonal direction will likely reduce the locking effect and lower the capacity of the masonry wall, making the results more reliable.

Furthermore, the smeared cracking model analyses showed similar results. In these analyses two diagonal crack bands developed, which was more in line with reality compared to the discrete cracking model. All analyses overpredicted the capacity of the masonry wall. This is likely due to the simplification of the physical model in DIANA. The wall was modelled as a homogeneous plane stress element, while in reality, the masonry is highly inhomogeneous. To get more realistic results this inhomogeneity will need to be modelled. This can be done by modelling both bricks and mortar and giving different material properties. This shows that the case study required careful consideration and experience in the field of modelling problems where numerical results are only available.
