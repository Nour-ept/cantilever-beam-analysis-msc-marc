# Cantilever Beam Analysis using MSC Marc

This repository contains a comprehensive analysis of a cantilever beam using MSC Marc, covering linear, nonlinear, and plastic deformation studies.

## Contents
- **Linear Analysis**: Evaluates initial response using small deformation and linear elastic theories.
- **Nonlinear Analysis**: Examines behavior under large deformations beyond the elastic limit.
- **Mesh Influence**: Studies the effect of different mesh densities on result accuracy.
- **Plastic Deformation**: Investigates behavior when load exceeds yield strength, causing permanent deformation.

## Objectives
- Understand the behavior of the cantilever beam under various loading conditions.
- Utilize MSC Marc for detailed analysis and modeling.
- Compare results from different mesh densities to evaluate accuracy.
- Assess the impact of plastic deformation on the beam.

## Model Description
- **Geometry**: 8 elements along the length, 1-2 elements deep.
- **Material Properties**: Young’s Modulus: 30.0×10⁶ lb/in², Yield Stress: 65,000 lb/in², Poisson’s Ratio: 0.3.
- **Loading**: Static load of 6000 lb applied at the free end.

## Software
- **MSC Marc and Mentat 2020**

## Analysis Steps
1. Create and mesh the model.
2. Assign material properties.
3. Apply boundary conditions.
4. Define the load.
5. Submit for analysis in MSC Marc.

## Results
- Displacement distributions
- Path plots
- History plots of displacement
- Global plastic strain plots

This repository provides a comprehensive case study for structural engineering analysis using MSC Marc, serving as a valuable resource for understanding cantilever beam behavior under various conditions.
