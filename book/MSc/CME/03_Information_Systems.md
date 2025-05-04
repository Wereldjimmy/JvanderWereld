# 3. Information Systems for the Construction Industry

During Q3 of my CME year, I also followed a course called Information Systems for the Construction Industry (CME4121) in which we were introduced to the possibilities and opportunities of BIM. The goal of the course was to show us how digital information systems can be utilised during the construction, operation, and maintenance of an asset. To do this, several software and techniques have been used on a specific project in the Netherlands.

**Our Case Study**\
As a project, my groupmate and I chose The Blox project in the Binckhorst, The Hague, the Netherlands. The Blox was at the time in construction and planned to be a 130-meter-tall residential tower consisting of 38 floors and 360 apartments, and started construction in July 2024.

**Created Artifacts**\
Firstly, a BIM model was created for The Blox using Revit 2025. Three systems were created (Structural, Architectural, and MEP) which were later merged into one model. 

```{figure} ../../figures/MSc/CME4121_3_Systems_Blox.png
---
width: 600px
align: center
---
Three models creating one BIM model
```

After this was done, a clash detection was performed using Autodesk Navisworks to identify all the clashes in our model. From all these clashes (267 initially), we picked three clashes to resolve by hand. The clashes that we picked had to do with the intersection between the components of the structural model and the MEP model. 

Then, a 5D simulation was made of The Blox in which the viewer can see how The Blox gets built up throughout time and with the development of the costs.

```{figure} ../../figures/MSc/CME4121_5D_Simulation.png
---
width: 500px
align: center
---
5D Simulation of The Blox
```

```{figure} ../../figures/MSc/CME4121_Cost_Development_Blox.png
---
width: 500px
align: center
---
Cumulative and Nominal Cost Development of The Blox
```

Then, a digital twin was created of The Blox for maintenance and asset management. In this digital twin several Internet of Things sensors were integrated that send their data towards a maintainability dashboard using Autodesk Tandem that supports decision making. 

```{figure} ../../figures/MSc/CME4121_Maintenance_Dashboard_Blox.png
---
width: 500px
align: center
---
Maintainability dashboard of The Blox
```

The BIM model was also created to do an ecological footprint calculation of The Blox using Autodesk Insight. This gave us another dashboard with the total amount of embodied carbon in the model.

```{figure} ../../figures/MSc/CME4121_Embodied_Carbon_Dashboard.png
---
width: 500px
align: center
---
Embodied Carbon Dashboard of The Blox
```

Safety is another thing that is very important in structures and where BIM can help. We chose a specific construction phase and created a virtual safety walkthrough showing several safety hazards. This helped us identify the hazards and come up with mitigations.

```{figure} ../../figures/MSc/CME4121_Safety_1.png
---
width: 500px
align: center
---
Safety mitigation example
```

At last, a BIM execution plan was created in which several arrangements and rules were set about the use and creation of the BIM model.