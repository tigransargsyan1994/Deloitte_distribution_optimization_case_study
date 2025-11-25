# Deloitte_distribution_optimization_case_study

This repository contains my solution to a distribution network optimization case study, prepared for an interview with Deloitte.

The objective of the case is to analyse and optimize the distribution of building materials from three production sites (Z1, Z2, Z3) to a set of customers, based on historical 2017 shipment data. All work is done in Python in a Jupyter Notebook, combining exploratory analysis, visualization and a linear optimization model.

## Contents

- **Jupyter Notebook**  
  The main notebook walks step by step through:
  - Data cleaning and preparation of expedition data and distance matrix.
  - Construction of derived variables (ton-km, costs, mode shares).
  - Descriptive analysis of the current network: site utilization, mode split, top customers, extra ton-km vs closest site, Sankey diagrams of flows.
  - Cost estimation based on assumed EUR/ton-km values for truck and train.

- **Optimization model (PuLP)**  
  A linear programming model is formulated to minimize total transport cost, subject to:
  - Satisfying each customer’s annual demand.
  - Not exceeding site capacities (with a chosen utilization limit).
  - Using only site–customer–mode combinations that actually existed in 2017.
  - Respecting historical train/truck shares per customer within a tolerance band.
  - Respecting train/truck shares per site (again within a tolerance band).
  - Special treatment of “train-only” customers.

  The optimized plan is compared against the 2017 baseline in terms of ton-km, costs, mode split and site utilization.

- **Exported results (Excel & plots)**  
  Key results are exported to Excel (flows by customer/site/mode, site summaries, customer-level cost comparison) together with a set of plots (PNG) used for the presentation.

## How to use

1. Open the main `.ipynb` notebook directly in GitHub to read the analysis.
2. To run the model yourself, clone the repository and install the required Python packages (pandas, numpy, matplotlib, plotly, pulp, etc.), then run the notebook in Jupyter.

