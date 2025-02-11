# Projects
This page contains the projects I did during my master's degree Structural Engineering at the Technical University Delft.

## Mathematical Optimization of Zandhazenbrug
or the course Programme Base (CIEM000)) of the master Structural Engineering, I was part of a team of four students, and we were tasked to optimise a project based on mathematical models considering several stakeholders, objectives and constraints. We chose to optimise the Zandhazenbrug near Muiderberg. 

**Stakeholder analysis**\
Firstly, a stakeholder analysis is done to map the stakeholders in a power-interest grid and gather all the requirements. These requirements where then used to set up several criteria for the multi-criteria decision analysis.

**Multi-Criteria Decision Analysis (MCDA)**\
The project started with doing a multi-criteria decision analysis to analyse three alternative solutions. The three design alternatives that were considered were:

1. Bridge without a center pillar
2. Tunnel under the highway
3. Bridge with a center pillar

From the MCDA software the original design (Bridge without centre pillar) emerged as the best option due to minimal disruption and optimal cost-effectiveness. Since we got the best design, we can optimize it using mathematical models.

**Design optimization**\
First, the design variables are determined. The first variable is the bridge span (x1) and the second variable is the bridge width (x2). The bridge span directly influences the traffic flow capacity of the highway underneath the bridge, while the bridge width influences the train frequency. Both the variables influence the material use, which in turn influence the cost and $CO_2$ emissions. The problem statement is depicted in the figure below.

```{figure} ../../figures/MSc/CIEM0000_Flowchart.jpg
---
width: 500px
align: center
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

1. Node
2. Elements
3. Constrainer

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