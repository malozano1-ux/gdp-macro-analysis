# Macroeconomic Drivers of U.S. Nominal GDP

Multiple linear regression study examining how five macroeconomic indicators — unemployment, inflation, the federal funds rate, money supply, and consumer confidence — influence U.S. nominal GDP across 241 monthly observations from 2004 to 2024.

## Overview

- **Course:** ECON 103L — Econometrics Lab, UCLA
- **Authors:** Manuela Lozano, Sebastian Farah, Miguel Quiñones
- **Tools:** R (`ggplot2`, `broom`, `patchwork`, `corrplot`, `car`, `lmtest`, `MASS`)
- **Data:** FRED (St. Louis Fed) + OECD Consumer Confidence Index
- **Date:** March 2025

## Methods

Built and evaluated multiple linear regression models using 241 monthly U.S. macroeconomic observations (2004–2024). The analysis included:

- Exploratory data analysis: histograms, correlation heatmap, scatterplot matrix, boxplots
- Full multiple linear regression (all 5 predictors)
- **VIF analysis** to detect multicollinearity
- **AIC model selection** across single-predictor and multi-predictor combinations
- **RESET test** to assess functional form misspecification
- Full regression diagnostics for each model (residuals vs. fitted, Q-Q, scale-location, leverage)

## Key Findings

- **Full model adjusted R² = 0.9777** — 98% of nominal GDP variation is explained by the five predictors
- **AIC selected the full model** (all 5 predictors) as optimal, with AIC = 3,839 and R² = 0.9782
- **Money supply (M2SL)** was the strongest positive predictor (β = 0.89, p < 0.001), consistent with monetary theory
- **Unemployment (UNRATE)** and **inflation (DEFLATOR)** negatively impacted GDP (β = −236.5 and β = −300.3), as expected
- **Federal funds rate** showed a surprising positive coefficient (β = 238.2), suggesting rate hikes coincided with expansion periods in this sample
- **VIF analysis** revealed multicollinearity; removing UNRATE collapsed R² from 0.9777 to just 0.1551, illustrating the trade-off between multicollinearity and predictive power
- **RESET test** (F = 55.69, p < 2.2e-16) confirmed model misspecification, indicating important non-linear relationships not captured by the linear form

## Files

| File | Description |
|---|---|
| `econ 103 final project.Rmd` | Full analysis: EDA, regression models, VIF, AIC, RESET test |
| `econ-103-final-project.pdf` | Rendered report with results and interpretation |
| `GDP - DATA.csv` | Monthly U.S. macroeconomic data (GDP, UNRATE, DEFLATOR, FEDFUNDS, M2SL, CCI) |

## Data Sources

All data sourced from public repositories:
- [FRED — St. Louis Fed](https://fred.stlouisfed.org/) (GDP, UNRATE, DEFLATOR, FEDFUNDS, M2SL)
- [OECD](https://www.oecd.org/en/data/indicators/consumer-confidence-index-cci.html) (Consumer Confidence Index)

## Full Report

[View on portfolio →](https://manuela-lozano.netlify.app/projects/gdp-macro.html)
