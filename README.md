# Gastric Cancer Survival Analysis

## Overview

This project performs a genome-wide survival analysis on primary gastric cancer patients to identify gene expression biomarkers associated with overall survival independently of clinical staging. The analysis uses publicly available data from the GEO repository (GSE84437) and combines Cox proportional hazards regression with false discovery rate correction.

## Data

**Dataset:** [GSE84437](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE84437)

- 433 patients with primary gastric cancer
- Illumina microarray gene expression data (quantile normalised)
- Clinical variables: age, sex, T stage, N stage, overall survival time, vital status

## Methods

- **Preprocessing:** probe-to-gene symbol mapping, duplicate probe collapsing (highest mean expression), log2 transformation
- **Covariate analysis:** Cox regression with age, sex, T stage, N stage; proportional hazards assumption tested via Schoenfeld residuals
- **Stage handling:** T1/T2 collapsed due to small group sizes; T stage and N stage stratified (rather than modelled as covariates) due to PH assumption violation
- **Gene screen:** genome-wide adjusted Cox regression (~20,000 genes), adjusting for age and stratifying by T/N stage; Benjamini-Hochberg FDR correction
- **Model diagnostics:** dfbeta influence plots, martingale residuals (linearity), deviance residual outlier detection, sensitivity analysis

## Key Finding

**LOXL4** (Lysyl Oxidase Like 4) was identified as significantly associated with worse overall survival independently of age and tumour stage (HR = 1.38 per SD, FDR < 0.05). LOXL4 encodes an extracellular matrix enzyme involved in collagen crosslinking and has previously been implicated in tumour invasion and metastasis across multiple cancer types.

## Limitations

Results are exploratory and require validation in an independent gastric cancer cohort before any clinical conclusions can be drawn.

## Requirements

```r
install.packages(c("survival", "survminer", "dplyr", "ggplot2", "forcats"))
BiocManager::install("GEOquery")
```

## Usage

Open `gastro-cancer-survival-ana.qmd` in RStudio and render with Quarto. The dataset is downloaded automatically from GEO on first run.
