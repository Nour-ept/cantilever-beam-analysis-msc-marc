# Full Analysis of a Cantilever Beam using MSC Marc

## Introduction

### Background
The analysis of cantilever beams is a fundamental topic in structural engineering, providing insight into the behavior of materials under various loading conditions. Cantilever beams, which are fixed at one end and free at the other, are commonly used in construction and mechanical applications due to their ability to withstand bending moments.

### Objective
The primary objective of this report is to perform a comprehensive analysis of a cantilever beam using MSC Marc software. This includes linear, nonlinear, and plastic deformation analyses. The analysis aims to understand the behavior of the beam under static loading conditions, utilizing small deformation theory and linear elastic theory.

### Model Description
In this exercise, the cantilever beam is subjected to a static load and analyzed using small deformation theory. The model consists of eight 2D plane stress, assumed strain, reduced integration (type 114) elements. These elements are uniformly spaced along the length of the beam, creating a mesh that is eight elements wide and one element deep. The assumed strain, reduced integration element is designed specifically for in-plane bending and is well-suited for this type of analysis.

### Material Properties
The beam material properties are defined as follows:
- Length, \( L \): 100.0 inches (2.54 meters)
- Width, \( a \): 1.0 inch (25.4 mm)
- Depth, \( b \): 2.0 inches (50.8 mm)
- Young's Modulus: \( 30.0 \times 10^6 \) lb/in² (207 GPa)
- Yield Stress: 65000 lb/in² (450 MPa)
- Poisson's Ratio: 0.3
- Applied Load, \( P \): 6000 lb (27200 N)

### Analysis Steps
The analysis follows a systematic approach to model creation, material property assignment, meshing, boundary condition application, load definition, and job submission for analysis in MSC Marc. Key steps include:
1. Creating a database and defining the geometry and mesh.
2. Assigning material properties and creating geometric properties.
3. Setting boundary conditions and defining the load.
4. Submitting the model for linear elastic analysis using MSC Marc.

### Software and Tools
The analysis is conducted using MSC Marc and Mentat 2020. No additional files are required, as all necessary data is generated within the software.

## Linear Analysis of Cantilever Beam

### Introduction
In this section, we perform a linear analysis of a cantilever beam to understand its behavior under static loading conditions. The linear analysis is essential for determining the initial response of the beam using small deformation theory and linear elastic theory.

### Methodology
The linear analysis was conducted using MSC Marc software. The following steps were taken:
1. **Model Creation**: A 100 x 2 quad surface cantilever geometry was created.
2. **Mesh Generation**: The model was divided into 8 x 1 quad mesh elements.
3. **Material Property Assignment**: Young's modulus was set to \(3 \times 10^7\), Poisson's ratio to 0.3, and mass density to 0.00074.
4. **Boundary Conditions**: The left edge of the beam was fixed in both the X and Y directions.

![Boundary Condition: Fixed](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/fixed.PNG)

5. **Loading**: A point load of 6000 lb was applied at the top right node in the negative Y direction.

![Boundary Condition: Tip Load](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/tipload.PNG)

6. **Analysis**: A linear static loadcase was created and submitted for analysis.

### Results
The results of the linear analysis are presented in the following figures. These include the Displacement distribution along the cantilever beam, the history plot, and the path plot.

![Displacement Distribution](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/model%20view%20linear.png?raw=true)

![Path Plot](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/path%20plot%20linear.png?raw=true)
*This plot illustrates the displacement along a path from the fixed end to the free end of the beam.*

![History Plot](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/historical%20plot%20linear.png?raw=true)
*This plot shows the displacement at the tip of the beam over the course of the analysis and the displacement Y is perfectly linear.*

## Nonlinear Analysis of Cantilever Beam

### Introduction
The purpose of the nonlinear analysis is to understand the behavior of the cantilever beam under large deformations, which small deformation theory does not accurately capture. This analysis is crucial for predicting the response of the beam to static loading conditions beyond the elastic limit.

### Methodology
The cantilever beam is modeled using eight 2D plane stress, assumed strain, reduced integration elements. These elements are uniformly spaced along the length of the beam, creating a mesh that is eight elements wide and one element deep.

1. **Open the Model**:
    - Load the existing model `tip_load.mud`.
2. **Create a Static Loadcase**:
    - Define a new static loadcase with a multi-criteria stepping procedure.
3. **Create Jobs for Nonlinear Analysis**:
    - Define a new job for structural analysis, selecting the previously created loadcase.
    - Ensure the analysis dimension is set to Plane Stress and disable Linear Elastic Analysis.
    - Select Large Strain in the analysis options.

### Results

![Model View for Nonlinear Analysis](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/model%20view%20non%20linear%20.png?raw=true)

![Path Plot for Nonlinear Analysis](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/path%20plot%20non%20linear.png?raw=true)

![History Plot for Nonlinear Analysis](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/history%20plot%20non%20linear%20.png?raw=true)

*The plot demonstrates a nonlinear relationship between displacement and time, indicating the effects of large deformation.*

## Mesh Influence on the Cantilever Beam Analysis

### Mesh Density and Model Description
For this analysis, the mesh density of the cantilever beam is increased to 8 elements along the length and 2 elements along the depth of the beam. This refinement is expected to provide more accurate results compared to the coarser 8x1 mesh.
- **Mesh Density**: 8 elements along the length, 2 elements along the depth
- **Element Type**: 2D plane stress, assumed strain, reduced integration elements

![Refined Mesh](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/mesch3.png?raw=true)

*The refined mesh is used to re-run the linear and nonlinear analysis and compare the results with those obtained using the coarser 8x1 mesh.*

### Results

![History Plot for Linear Analysis with 8x2 Mesh Density](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/history%20plot%20linear%20linear.PNG?raw=true)
*The plot shows a linear relationship between displacement and time.*

![History Plot for Nonlinear Analysis with 8x2 Mesh Density](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/history%20noon%20.png?raw=true)

*The plot demonstrates a nonlinear relationship between displacement and time, indicating the effects of large deformation.*

The results of the nonlinear analysis with the refined 8x2 mesh density are compared to those obtained with the coarser 8x1 mesh:

| Mesh Density | Small Deflection (in) | Large Deflection (in) |
|--------------|------------------------|-----------------------|
| 8x1          | -99.64                 | -59.78                |
| 8x2          | -98.92                 | -59.66                |

*Table: Comparison of Deflection Results for Different Mesh Densities*

The comparison of results between the 8x1 and 8x2 mesh densities demonstrates the impact of mesh refinement on the accuracy of the analysis. Generally, a finer mesh provides a more accurate representation of the beam's behavior under large deformations. This is particularly important in nonlinear analysis, where the effects of large strain and rotation are significant.

## Plastic Deformation of Cantilever Beam

### Introduction
Analyzing the plastic deformation of a cantilever beam is essential for understanding its behavior beyond the elastic limit. When the applied load exceeds the yield strength of the material, the beam undergoes permanent deformation. This section presents a comprehensive plastic deformation analysis using MSC Marc software to capture the nonlinear material response under static loading conditions.

### Methodology
The plastic deformation analysis of the cantilever beam was conducted through a systematic approach involving the following steps:

#### Material Property Assignment
The plastic material properties assigned to the beam included:
- Young’s Modulus: $30 \times 10^6$ lb/in² (207 GPa)
- Yield Stress: 65,000 lb/in² (450 MPa)
- Poisson’s Ratio: 0.3

A plastic property table was created using the `eq_plastic_Strain` table, considering a 10% slope of the elastic range to define the plastic region.

#### Mesh Refinement
The mesh was subdivided into smaller elements to enhance the accuracy of the analysis. A refined mesh density of 4 x 16 elements was utilized.

![Subdivided Mesh](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/new%20mesh.PNG?raw=true)

### Results
The plastic deformation analysis yielded significant insights into the permanent deformation behavior of the cantilever beam under the applied load.

#### Y Displacement Plot
The Y displacement plot illustrated the deformation of the beam under the applied load, highlighting the maximum displacement areas and providing a visual comparison between the initial and deformed shapes.

![Y Displacement Plot](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/model%20plastic%20.png?raw=true)

#### Global Plastic Strain Plot
The global plastic strain plot offered a comprehensive view of the plastic deformation across the entire beam, facilitating an understanding of the material's overall plastic response under the applied load.

![Global Plastic Strain Plot](https://github.com/Nour-ept/cantilever-beam-analysis-msc-marc/blob/main/equivalent%20of%20global%20plastic%20strain.png?raw=true)

## Conclusion
The plastic deformation analysis of the cantilever beam using MSC Marc provided a thorough understanding of the material behavior beyond the elastic limit. By capturing the nonlinear and plastic properties of the material, the analysis offered valuable insights into the beam's permanent deformation under static loading conditions. This information is critical for the design and evaluation of cantilever beams in various structural engineering applications, ensuring their reliability and integrity under different loading scenarios.
