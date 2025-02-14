# Mathematical Optimization of Zandhazenbrug
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
First, the design variables are determined. The first variable is the bridge span (x1) and the second variable is the bridge width (x2). The bridge span directly influences the traffic flow capacity of the highway underneath the bridge, while the bridge width influences the train frequency. Both the variables influence the material use, which in turn influence the cost and $CO_2$ emissions. The problem statement is depicted in the figure below.

```{figure} ../../figures/MSc/CIEM0000_Flowchart.png
---
width: 500px
align: center
---
Problem statement visualisation
```

The next step was to create linear objective functions that rate the performance of a design and constraints. This resulted in a solution space which is depicted in the figure below.

```{figure} ../../figures/MSc/CIEM0000_Solution_Space.png
---
width: 350px
align: center
---
Solution space
```

The last step of the optimization was to perform a Multi-Objective Design Optimization (MODO). The IMAP and MINMAX algorithms were used to find the optimal design that balances stakeholders needs. The result of the algorithms is shown in the figure below. 

```{figure} ../../figures/MSc/CIEM0000_Optimal_Solution.png
---
width: 800px
align: center
---
Optimal design solution using both algorithms
```

After running the MCDA for both design solutions, it turns out that the MINMAX solution was the best solution with a span of 276.1 m and a width of 10.6 m. 

During this project I learned that everyday decisions can be optimized using mathematical models and that it is very important to listen to stakeholder requirements.