# TWOLINK_NODYCON

This repository contains the numerical continuation data, multi-impact simulations, and visualization scripts accompanying the research article, [The Effect of Gait Stability Based on Two Types of Impact Strategies for Two-Link Walking and Brachiating Robots](https://arxiv.org/abs/2610.01004).  The paper was presented at NODYCON 2026.  A prerecorded version of the presentation is archived on [Cassyni](https://cassyni.com/events/KqyjMJLcFDtJvfqMV7w1z5).

This research was co-authored by Alan Ruben Estrada Flores and Dr. Nelson Rosa Jr. at the Illinois Institute of Technology.

## Repository Contents

### Core Simulation & Computation
* **`ComputeGaitFamilies.nb`**: A Mathematica notebook dedicated to calculating the initial gait families and generating the raw numerical continuation data.
* **`BranchImpacts.nb`**: A notebook containing the code for simulating repeated impacts on a family of gaits. It simulates gaits across 1,000 impacts to analyze the impact sequence and the long-term evolution of unstable gaits depending on the switching strategy.
* **`TwoLink/`**: A custom Wolfram package containing the core dynamic simulation functions utilized across the notebooks.

### Plotting Scripts
* **`Plots.nb`**: A Mathematica notebook that generates Figures 2, 4, and 5 for the paper. It conducts a bifurcation analysis for the BUone (brachiating underhand) gait family. This includes mapping period-doubling (PD) bifurcations under state-based switching, as well as Neimark-Sacker (NS) and fold (FD) bifurcations under time-based switching. It also visualizes the convergence of unstable points to closed invariant curves or stable gaits on mirrored families.
* **`Plots2.nb`**: A Mathematica notebook containing the code to generate Figures 1, 3, and 6 for the paper. It processes continuation data to map the stable and unstable regions for both time-based and state-based switching, and generates the resulting physical gait diagrams and bifurcation plots.

### Datasets
* **`out.wl`**: A Mathematica data file containing the raw numerical continuation output for the various gait families. `Plots2.nb` loads this file to construct the foundational gait space curves before plotting.
* **`Z_Plots.wl`**: A data file generated and used by `Plots2.nb` to store multi-impact simulation trajectories (Poincaré section states). Caching this data allows the notebook to rapidly plot period-doubling bifurcations and stability boundaries without re-running the underlying differential equation solvers.
* **`TimeImpactsBUone.wxf` & `StateImpactsBUone.wxf`**: Data files containing the imported results of multi-impact simulations on the brachiating gait family under time-based and state-based switching, respectively.
* **`TimeBranches.m` & `StateBUone.m`**: Datasets containing the initial brachiating gait family data, including the respective switching eigenvalues for both strategies.

### Figures
* **`two_link_model.pdf`**: A TikZ-generated diagram of the physical two-link robotic model, illustrating joint angles, slope, and coordinate frames.
* **`gtb.pdf`**: A generated plot illustrating gait families for time-based (tb) switching.
* **`gsb.pdf`**: A generated plot illustrating gait families for state-based (sb) switching.
* **`sb-multi.pdf`**: A composite plot visualizing the sb  walking gait space, featuring inset zooms that map unstable walking gaits across multiple impacts to period-doubling brachiating gaits.

* **`bo.pdf`**: A generated kinematic visualization of the Brachiating Overhand gait.
* **`bu.pdf`**: A generated kinematic visualization of the Brachiating Underhand gait.
* **`wo.pdf`**: A generated kinematic visualization of the Walking Overhand gait.
* **`wu.pdf`**: A generated kinematic visualization of the Walking Underhand gait.

## Requirements
* **Wolfram Mathematica**: Required to open and execute the `.nb` notebooks and load the `TwoLink` package.

## Usage
To reproduce the figures and analyze the continuation branches:
1. Clone the repository to your local machine.
2. Ensure the `TwoLink` package and all `.wl`, `.m`, and `.wxf` data files are accessible in the same working directory.
3. Open `Plots2.nb`, `Plots.nb`, or `ComputeGaitFamilies.nb` in Mathematica and evaluate the notebook to generate the corresponding plots and diagrams.
