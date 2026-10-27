# Bayesian modelling of CO₂ emissions

Academic team project exploring the association between per-capita CO₂ emissions and economic, energy and demographic variables using Bayesian regression and model averaging in R.

**Authors:** Kalisto Willaey, Leonard Nader, Andrea Barbui and Federico Croci, as listed in the source analysis. The repository represents team work; individual component ownership is not specified.

## Start here

Read the [analysis report](Final_Project.pdf), or inspect the [main R Markdown source](Final_Project.Rmd) and [variable-transformation exploration](Variable_Transformations.Rmd).

## Methods

- Exploratory distributions, correlations and transformations.
- Bayesian linear regression with g-prior and Jeffreys–Zellner–Siow prior variants.
- Model comparison using BIC and Bayesian Model Averaging with the `BAS` package.
- Posterior coefficient summaries, uncertainty intervals and predictive analysis.

The analysis considers how the relationship between GDP and emissions changes when energy use and other covariates are included. These are model-dependent associations, not causal estimates.

## Data and execution

The source expects `data/CO2.csv`, an assignment-specific extract attributed to Our World in Data. That extract is not included, and a current upstream download may differ from the original data.

To recreate the analysis, obtain the original extract, place it at the expected path and open `Final_Project.Rmd` in RStudio or another R Markdown environment. The main source imports `Metrics`, `BAS`, `tidyverse`, `ggplot2`, `corrplot`, `GGally`, `dplyr`, `moments`, `fastDummies`, `broom` and `gridExtra`.

Choose the preprocessing branch deliberately: the optional outlier-removal/standardisation block changes the assumptions of subsequent log transforms, and source comments call for corresponding adjustments. Some later row selections are hard-coded to the original data dimensions. This is an exploratory analysis requiring review of those choices, rather than a turnkey script for arbitrary data.

## Limitations

The original dataset and a tested environment lockfile are absent. Reported findings are historical and have not been rerun for this documentation update. Preprocessing choices, multicollinearity and the selected observations affect the posterior and predictive conclusions.
