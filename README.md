# A Nonparametric Penalized Likelihood Approach to Density Estimation of Space-Time Point Patterns

This repository contains the code and data accompanying Begu et al. (2024), published in *Spatial Statistics*. The paper introduces **STDE-PDE**, a nonparametric method for estimating how the distribution of events evolves continuously in space and time on irregular planar regions and curved surfaces.

**[Code and data](./%5B2024%5D_begu_et_al__spatial_statistics)** · **[Published article](https://doi.org/10.1016/j.spasta.2024.100824)**

## Method

The data consist of event locations and occurrence times. The estimator uses penalized maximum likelihood to recover a joint space–time density. Separate roughness penalties, defined through differential operators in space and time, control smoothing along each dimension.

The numerical implementation combines **finite elements in space** with **B-splines in time**. The spatial mesh represents the geometry of the observation region, including irregular boundaries, concavities, and holes. The resulting estimator can capture multiple peaks, directional patterns, and changes in their location and concentration over time. The paper also develops tools for quantifying uncertainty in the estimated density.

## Theoretical results

The paper establishes well-posedness of the penalized estimation problem and proves consistency of the estimator under the stated assumptions. It also establishes the link between estimation of a normalized space–time density and estimation of the intensity of an inhomogeneous space–time Poisson point process.

## Simulation studies and applications

The simulation studies evaluate the estimator against competing methods on point patterns with known densities. Two applications illustrate the method on observed data:

- **Gastrointestinal infections.** The analysis examines the evolution of the spatial distribution of reported infections.
- **Worldwide earthquakes.** The analysis estimates the density of earthquakes with magnitude greater than 4.75 from 2020 to 2022 on the Earth's surface.

The [2024 paper folder](./%5B2024%5D_begu_et_al__spatial_statistics) contains the supplementary materials for reproducing the simulation and application results.

## Citation

Begu, B., Panzeri, S., Arnone, E., Carey, M., & Sangalli, L. M. (2024). A nonparametric penalized likelihood approach to density estimation of space-time point patterns. *Spatial Statistics, 61*, 100824. https://doi.org/10.1016/j.spasta.2024.100824
