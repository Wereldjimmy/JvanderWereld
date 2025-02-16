# 2. Coding the Matrix Method in Python
The matrix method is a widely used method to determine forces, displacements, and stresses in engineering structures and is the basis for computational analysis. It is widely applied in analysing beams, trusses, and frames by representing the system as a set of linear equations. As part of the course Slender Structures (CIEM5000) I was tasked to write the matrix method in Python and apply it to a complex structure.

**Writing code**\
A big part of the assignment was to write the code of the matrix method in Python. We were given the beginning of a code, but our task was to finish it and include a different type of loading (a distributed sine load) to analyse the structure given below.

```{figure} ../../figures/MSc/CIEM5000_MM_Structure.png
---
width: 700px
align: center
---
Structure that is analysed using the Matrix Method
```

Object-orientated programming was used to write the code and make it easily applicable to a lot of structures. The code can be divided into three separate parts:

1. Node class
2. Element class
3. Constrainer class

The **Node class** was used to store node information and keep track of the total number of Degrees of Freedom (DOFs) of the problem. 

The **Element class** kept track of each element in the model, including cross-section properties, element orientation, and the nodes that make up each element. The element class was responsible for providing the element stiffness matrix in the global coordinate system and postprocessing element-level fields. The class described an element combining extension and Euler-Bernoulli or Timoshenko bending and can output displacements and bending moments.

At last, the **Constrainer class** represents a constrainer for fixing degrees of freedom in a structural analysis. This class is able to fix a DOF of a node, fix the displacement of a node, and output the support reaction forces of the model.

**Result**\
The result of the report was the fully displaced structure, moment line of the structures, and support reactions.

```{figure} ../../figures/MSc/CIEM5000_MM_Result.png
---
width: 700px
align: center
---
Result of the Matrix Method analysis
```