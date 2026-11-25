# STDE-PDE reproducibility materials

R code accompanying Begu et al. (2024), [*A Nonparametric Penalized Likelihood Approach to Density Estimation of Space-Time Point Patterns*](https://doi.org/10.1016/j.spasta.2024.100824), *Spatial Statistics*, 61, 100824.

This folder contains six simulation studies and two data applications. The simulations examine space–time density estimation on planar regions, the sphere, and a non-spherical surface. One simulation also illustrates intensity estimation for an inhomogeneous Poisson process. The applications examine gastrointestinal infections in Southampton and earthquakes worldwide.

## Requirements

The scripts call `DE.FEM.time()` from the **fdaPDE 1.1.x R package**. The companion library scripts specify version **1.1-16 or later**. The newer `fdaPDE-R` GitHub wrapper has a different interface.

Each analysis has a `libraries_*.R` file listing its R package dependencies and a `helper_functions_*.R` file defining analysis-specific functions. Check the library file for the analysis you want to run. Keep any accompanying `data/`, `mesh/`, and `map/` directories in place.

## Running an analysis

Download or clone the repository. In a fresh R session, set the working directory to the folder of the analysis you want to run. The scripts use paths relative to that folder and source their companion files automatically. For example, from the directory containing `STDE-PDE`:

```r
setwd("STDE-PDE/[2024]_begu_et_al__spatial_statistics/simulation_1")
source("simulation_1.R")
```

- **Simulations.** The scripts include a `generate.data()` step and then read the generated sample files. On a first run, use the generation step before fitting. Keep the generated files if you want to reuse the same samples.
- **Applications.** `application_1.R` reads `data/data.RData` for the Southampton analysis. `application_2.R` reads `data/query_4.75.csv` for the earthquake analysis and uses files in `mesh/` to represent the globe.
- **Outputs.** Several scripts save fitted estimates, error summaries, and timing results in `output/` and write plots to `pictures/`. If you run a plotting section on its own, first check which saved objects it loads.

## Scripts and corresponding figures

| Paper section | Entry script | What it does | Figures |
| --- | --- | --- | --- |
| §6.3 | [`simulation_1.R`](simulation_1/simulation_1.R) | Estimates a mixture of time-dependent Gaussian distributions on a square. | 4, 5 |
| §6.4 | [`simulation_2.R`](simulation_2/simulation_2.R) | Estimates a mixture of time-dependent Kent distributions on the sphere. | 7, 8 |
| §6.5 | [`simulation_3.R`](simulation_3/simulation_3.R) | Estimates a highly localized and skewed space–time density on the sphere. | 9, 10 |
| §7.1 | [`application_1.R`](application_1/application_1.R) | Analyses the changing spatial distribution of reported gastrointestinal infections in Southampton. | 1, 3 (left), 11, 12 (left) |
| §7.2 | [`application_2.R`](application_2/application_2.R) | Estimates the space–time density of worldwide earthquakes with magnitude greater than 4.75 from 2020 to 2022. | 2, 3 (right), 12 (right), 13 |
| Appendix F | [`simulation_4.R`](simulation_4/simulation_4.R) | Illustrates intensity estimation for an inhomogeneous Poisson process. | F.14 |
| Appendix G | [`simulation_5.R`](simulation_5/simulation_5.R) | Evaluates density estimation in an additional planar simulation. | G.15, G.16 |
| Appendix H | [`simulation_6.R`](simulation_6/simulation_6.R) | Estimates the density of a simulated point pattern on a non-spherical two-dimensional manifold. | H.17–H.19 |

## Citation and contact

Begu, B., Panzeri, S., Arnone, E., Carey, M., & Sangalli, L. M. (2024). A nonparametric penalized likelihood approach to density estimation of space-time point patterns. *Spatial Statistics, 61*, 100824. https://doi.org/10.1016/j.spasta.2024.100824

Blerta Begu and Simone Panzeri contributed equally to this work. If you have questions about the code or how to reproduce the results, feel free to contact either of us.
