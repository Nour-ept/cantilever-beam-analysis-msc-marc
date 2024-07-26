# Full Analysis of a Cantilever Beam using MSC Marc

## Introduction

### Background
The analysis of cantilever beams is a fundamental topic in structural engineering, providing insight into the behavior of materials under various loading conditions. Cantilever beams, fixed at one end and free at the other, are commonly used in construction and mechanical applications due to their ability to withstand bending moments.

### Objective
The primary objective of this report is to perform a comprehensive analysis of a cantilever beam using MSC Marc software, including linear, nonlinear, and plastic deformation analyses. This aims to understand the behavior of the beam under static loading conditions, utilizing small deformation theory and linear elastic theory.

### Model Description
- **Length, L**: 100.0 inches (2.54 meters)
- **Width, a**: 1.0 inch (25.4 mm)
- **Depth, b**: 2.0 inches (50.8 mm)
- **Young’s Modulus**: 30.0×10⁶ lb/in² (207 GPa)
- **Yield Stress**: 65,000 lb/in² (450 MPa)
- **Poisson’s Ratio**: 0.3
- **Applied Load, P**: 6,000 lb (27,200 N)

### Analysis Steps
1. Creating a database and defining the geometry and mesh.
2. Assigning material properties and creating geometric properties.
3. Setting boundary conditions and defining the load.
4. Submitting the model for linear elastic analysis using MSC Marc.

### Software and Tools
- MSC Marc and Mentat 2020

## Analysis Details

### Linear Analysis
- **Methodology**: Model creation, mesh generation, material property assignment, boundary conditions, and loading.
- **Results**: Displacement distribution along the cantilever beam, path plot, and history plot of Y displacement at the beam tip.

### Nonlinear Analysis
- **Methodology**: Static loadcase with multi-criteria stepping procedure, structural analysis job setup, and large strain analysis.
- **Results**: Model view, path plot, and history plot of Y displacement indicating large deformation effects.

### Mesh Influence on the Analysis
- **Methodology**: Increased mesh density from 8x1 to 8x2 elements.
- **Results**: Comparison of deflection results for different mesh densities, showing improved accuracy with finer mesh.

### Plastic Deformation Analysis
- **Methodology**: Assignment of plastic material properties, mesh refinement to 4x16 elements.
- **Results**: Y displacement plot and global plastic strain plot illustrating permanent deformation behavior under applied load.

## Conclusion
The analysis using MSC Marc provided a thorough understanding of the cantilever beam’s behavior under various loading conditions. The results from linear, nonlinear, and plastic deformation analyses offer valuable insights for structural engineering applications, ensuring the reliability and integrity of cantilever beams.


