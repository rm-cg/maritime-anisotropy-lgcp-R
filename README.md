# Evaluating Monsoonal Anisotropy in Maritime Congestion Fields via Spatial Point Process Modeling of Satellite-Derived Vessel Distributions

**Author:** Ruth Margareth C. Guinto, Bachelor of Science in Mathematics  
**Institution:** Pamantasan ng Lungsod ng Maynila, College of Science  
**Date:** March 2027

## 📌 Project Overview
This repository contains the datasets and source code for analyzing the directional mechanics governing maritime traffic congestion within **Manila Bay**. The research conceptualizes observed vessel locations as a realization of a stochastic **Spatial Point Pattern** within a bounded, non-convex marine observation window. 

The spatial configuration and varying intensity of maritime traffic are driven by exogenous spatial covariates (Bathymetry, Anchorage Proximity) and modeled via a **Log-Gaussian Cox Process (LGCP)** to evaluate structural bottlenecks and monsoonal geometric anisotropy (Habagat vs. Amihan).

---

## 📂 Repository Contents
This repository strictly hosts the code and datasets required for mathematical reproducibility. The full written thesis manuscript and posters remain private.

*   `01_maritime_anisotropy_LGCP.ipynb`: The primary executable R script (Jupyter Notebook format). Contains the full spatial point process pipeline, including non-convex window generation, spatstat intensity mapping, and INLA/inlabru SPDE mesh optimization.
*   `DATASETS/`: Contains historical spatial point pattern CSV files.
    *   **Proxy Data:** Global Fishing Watch (GFW) vessel detection datasets (Habagat and Amihan seasonal splits).
    *   **Local Data:** Philippine Space Agency (PhilSA) DALOI radar matrices (Pending Integration / Plug-and-Play architecture).
*   `readme_public-*.md`: Official data dictionaries and metadata files associated with the GFW proxy datasets, maintaining data versioning transparency.

---

## ⚙️ Technical Stack & Environment
To eliminate configuration conflicts and maximize stability for heavy spatial packages, this pipeline is built natively in **pure R** using a dedicated cloud kernel, completely bypassing Python integration. 

**Core R Dependencies:**
*   `spatstat` (Spatial Point Pattern Analysis and Minimum Contrast Estimation)
*   `sf` (Simple Features for handling non-convex marine boundaries)
*   `inlabru` / `INLA` (Stochastic Partial Differential Equation (SPDE) approximation and Bayesian inference)
*   `geodata` (Coastline extraction)

**Execution Environment:** 
*   Google Colab (Native R Runtime Kernel)

---

## 📊 Data Sourcing & Citation
The proxy maritime traffic data utilized in the initial phases of this pipeline is provided by **Global Fishing Watch (GFW)**. The GFW datasets are subject to change due to algorithm updates and are verified via the included GFW readmes. 

**Mandatory Academic Citation for Proxy Data:**
> Kroodsma, D. A., Mayorga, J., Hochberg, T., Miller, N. A., Boerder, K., Ferretti, F., Wilson, A., Bergman, B., White, T. D., Block, B. A., Woods, P., Sullivan, B., Costello, C., & Worm, B. (2018). *Tracking the global footprint of fisheries.* Science, 359(6378), 904-908. https://doi.org/10.1126/science.aao5646

**License:** 
The proxy spatial datasets from Global Fishing Watch are licensed under the **Creative Commons Attribution-ShareAlike 4.0 International License** for non-commercial academic use. Code assets associated with GFW are licensed under Apache 2.0.
