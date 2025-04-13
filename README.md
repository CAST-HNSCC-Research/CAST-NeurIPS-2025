# CAST: Time-Varying Treatment Effects with Application to Radiotherapy on Head and Neck Squamous Cell Carcinoma

This repository contains the implementation used to estimate **time-varying treatment effects** in survival analysis using **causal survival forests** and temporal modeling. The method models both **survival probabilities** and **restricted mean survival times (RMST)**, enabling interpretable, dynamic estimation of treatment benefit over time.

## Overview

The main script, `Final_novel_R_propensity_EY.r`, performs the following:

- **Simulates or loads patient data** with time-to-event outcomes
- **Calculates biologically effective dose (BED)** metrics for radiotherapy
- **Estimates propensity scores** via elastic net logistic regression
- **Fits causal survival forests** at multiple time horizons to estimate individualized treatment effects
- **Visualizes treatment effect distributions** and Kaplan-Meier curves
- **Models the temporal trajectory of treatment effects** using both parametric (quadratic) and nonparametric (spline) approaches
- **Computes SHAP values** to interpret which covariates explain treatment effect heterogeneity
- **Performs sensitivity analyses** including:
  - Dummy outcome tests
  - Refutation tests with synthetic confounders
  - Noise variable injection
  - Negative control causal variables

## Key Files

- `Final_novel_R_propensity_EY.r`: Main analysis script (fully self-contained)
- `real_data.csv`: Preprocessed clinical dataset (loaded within script)
- Output files include:
  - `.csv` results for estimated treatment effects, SHAP values, model diagnostics
  - `.png` visualizations for effect trajectories, SHAP plots, KM curves, and correlation heatmaps

## Dependencies

This script uses the following R packages: caret, car, boot, pscl, tidyverse, Hmisc, psych, survival, survminer, pdp, glmnet, grf, devEMF, matrixStats, vioplot, fastshap, MASS, corrplot, GGally, dplyr


Please ensure these are installed prior to running the script.

## Reproducibility

The script is designed to be **fully reproducible** with fixed random seeds. Results may take some time to generate due to the large number of trees and refutation tests.

## Citation

This implementation is part of a submission under anonymous review for a machine learning conference. Please contact the authors upon publication for full attribution.

