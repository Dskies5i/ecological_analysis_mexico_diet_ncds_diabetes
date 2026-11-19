# Ecological Time-Series & Dietary Shift Analysis: NOVA Food Groups and Chronic Disease Rates in Mexico (1984–2024)

## Overview
This project explores multi-decade ecological relationships between ultra-processed food (UPF) consumption, NOVA dietary shares, population-adjusted disease incidence rates, and chronic/metabolic health indicators in Mexico. All source datasets were compiled and structured from official government publications, public health yearbooks, and dietary survey series, with irregular year intervals reflecting original source availability rather than missingness.

## What This Analysis Covers
- **Data Compilation & Normalization:** Merging multi-year morbidity/disease records, population denominators, and NOVA dietary share series (`pct_kcal_unprocessed`, `pct_kcal_ingredients`, `pct_kcal_processed`, `pct_kcal_ultra_processed`, and total kilocalories) into rates per 100,000 population.
- **Long-Term Trends vs. Short-Term Coupling:** Comparing correlations in **levels** (capturing long-run secular trajectories) against **first differences ($\Delta-\Delta$)** (capturing step-to-step changes across available survey/reporting waves).
- **Diagnostic & Time-Series Exploration:** Evaluating stationarity, regression fits with confidence intervals, correlation heatmaps, and cross-disease coupling patterns.

## Visual Highlights

### 1. NOVA Dietary Shifts & Total Energy Over Time
Tracks the long-term rise in ultra-processed food caloric share alongside shifts across unprocessed foods, culinary ingredients, processed foods, and total kilocalories.

![NOVA Dietary Shares and Total Calories](results/Consumption%20of%20unprocessed%20foods_ingredients_etc.jpg)

### 2. Levels vs. Short-Term ($\Delta-\Delta$) Diet–Disease Relationships
Contrasts long-run correlations in **levels** against step-to-step correlations in **first differences ($\Delta-\Delta$)** across NOVA dietary shares and disease incidence rates.

![Levels Correlation Heatmap](results/Levels%20Correlation%20Heatmap:%20Dietary%20Changes%20vs%20Disease%20Rate%20Changes.jpg)

![First Differences Correlation Heatmap](results/First%20differences%20Correlation%20Heatmap:%20Dietary%20Changes%20vs%20Disease%20Rate%20Changes.jpg)

### 3. Short-Term Coupling & Cross-Disease Co-Movement
Examines OLS linear coupling with a 95% confidence band between $\Delta\text{UPF}$ and $\Delta\text{Diabetes Total}$ alongside inter-disease correlations in first differences.

![Short-Term Coupling: Diabetes Total vs UPF](results/C2B_diabetes_coupling_with_CI.jpg)

![First Differences Correlation Matrix of Chronic Disease Rates](results/first_differences_correlation%20heatmap%20of%20chronic%20disease%20rates.jpg)

![First Differences Coupling: Diabetes Total vs Chronic Diseases](results/First%20differences%20Coupling:%20Diabetes%20Total%20vs%20Chronic%20Diseases%20(Full%20Dataset).jpg)

## Repository Structure
- `starting_dbs/` — Core compiled input datasets (`diseases_1984_2024.csv`, `population_mexico_1984_2024.csv`, `nova_1984_2024.csv`).
- `notebooks/` — Exploratory and analytical Jupyter notebooks covering rate calculation, NOVA trends, and coupling analysis.
- `results/` & `old_results/` — Generated summary tables, merged analytical datasets, and exported figures.
- `muertes_inegi/` — Supplementary mortality/INEGI reference files.

## Key Analytical Notes & Limitations
- **Ecological Design:** Aggregate population-level associations describe macro-level patterns over time and do not establish individual-level causality.
- **Irregular Survey Intervals & Reporting Eras:** Because underlying government PDFs and dietary waves occur at uneven intervals and specific conditions/subtypes begin in different years, pairwise sample sizes vary by series and should be interpreted alongside exact year coverage.

## Tools & Stack
- Python (`pandas`, `numpy`, `scipy`, `statsmodels`, `matplotlib`, `seaborn`)
- Jupyter Notebooks
