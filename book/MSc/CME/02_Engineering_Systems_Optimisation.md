# 2. Engineering System Optimisation

During Q3 of my CME year, I followed a course called Engineering System Optimisation (CME4501) in which we explored several optimisation techniques and applied them to a project. The goal of this course was to translate an engineering-related problem into a goal-oriented mathematical optimisation model with the use of Python. This engineering problem was then used to explore and evaluate the quality of different exact and (meta)heuristic methods to provide a valid solution while considering the trade-offs between resource requirements and the quality of the solution. 

**Our Case Study**\
We, my groupmate and I chose to investigate the Fehmarnbelt Tunnel. The Fehmarnbelt Tunnel is an ambitious infrastructure project connecting Denmark and Germany via an 18-kilometre immersed tunnel beneath the Baltic Sea. Once completed, it will be the world's longest immersed tunnel, carrying both road and rail traffic. The tunnel aims to significantly reduce travel times, strengthen economic ties between Scandinavia and Central Europe, and provide a sustainable alternative to ferry and air transport across the Fehmarn Belt strait.

**Optimisation Method**\
The investigation into the optimisation of the Fehmarnbelt Tunnel involved formulating and solving a nonlinear constrained optimization problem. The method focused on minimizing the total cost of the tunnel and the total $CO_2$ emissions that would be emitted during operation and construction. The optimisation included three design variables (number of lanes, segment length, and toll fare) and three constraints (travel time, emissions during construction, and cost return). The problem was solved with the help of Python and the Differential Evolution function of the `Scipy` package. This method is stochastic and does not use gradient methods to find the minimum. 

With the results, a Pareto Front was created that could be used by the client (Femern A/S) to make decisions about the design.

**Results**\
With the results from the optimisation the following Pareto Front was created:

```{figure} ../../figures/MSc/CME4501_pareto_front.png
---
width: 500px
align: center
---
Pareto Front
```

Furthermore, the values of the constraints and optimised variables were analysed:

```{figure} ../../figures/MSc/CME4501_constraint_values.png
---
width: 500px
align: center
---
Constraint values
```

```{figure} ../../figures/MSc/CME4501_optimised_variables.png
---
width: 500px
align: center
---
Optimised variable values
```