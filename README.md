# Milwaukee County Equity Analysis Using Census Microdata (PUMS)

## Overview

This repository contains a fully reproducible analysis of **poverty and housing cost burden in Milwaukee County**, using the **American Community Survey (ACS) Public Use Microdata Sample (PUMS)**.

The project demonstrates how Census microdata can be used to examine **compounding disadvantage** across overlapping characteristics — including **race and ethnicity, disability status, and nativity** — in ways that are not possible using standard pre-tabulated Census tables.

All data processing, weighting, analysis, and visualization steps are documented and automated in R. The complete codebase is included to ensure transparency and reproducibility.

---

## Purpose

Nonprofits and county agencies frequently rely on Census data to support:
- equity-focused planning
- grant applications and reporting
- program targeting and evaluation

While ACS summary tables are appropriate for many uses, they are limited when the research question involves **multiple interacting characteristics**. This project uses microdata to illustrate how poverty and housing stress are distributed across **intersectional groups**, providing insight that is directly relevant to state-funded, county-administered programs.

---

## Key Questions

- How do poverty rates differ across intersectional groups defined by race/ethnicity, disability, and nativity?
- Which renter households experience the highest levels of housing cost burden?
- How do overlapping characteristics compound economic vulnerability in Milwaukee County?

---

## Data Sources

- **American Community Survey (ACS) 2022 Public Use Microdata Sample (PUMS)**  
  U.S. Census Bureau

- **Geographic correspondence (PUMA to County)**  
  Missouri Census Data Center (Geocorr 2022)

---

## Geographic Methodology

### Public Use Microdata Areas (PUMAs)

For privacy protection, Census microdata is released at the **Public Use Microdata Area (PUMA)** level rather than at finer geographies such as census tracts or counties. Each PUMA contains approximately 100,000 or more residents.

Milwaukee County does not align perfectly with a single PUMA.

### County-Level Estimation

To approximate Milwaukee County results, this project applies **official geographic allocation factors** from the Missouri Census Data Center. These factors indicate the share of each PUMA’s population located within Milwaukee County.

Survey weights are adjusted using these allocation factors to produce **Milwaukee County–specific estimates**.

> Results should be interpreted as statistically robust estimates intended to identify patterns and disparities, not as exact administrative counts.

---

## Analytical Approach

### Population Groups

Individuals and households are categorized using an **intersectional framework** based on:
- Race and ethnicity
- Disability status
- Nativity (U.S.-born vs. foreign-born)

### Outcomes Examined

- **Poverty status**, based on Census poverty thresholds
- **Housing cost burden**, defined as:
  - Spending 30% or more of household income on rent
  - Spending 50% or more of household income on rent (severe burden)

Housing cost burden is calculated using **annual household income and annualized housing costs**, consistent with Census and HUD guidance.

---

## Reproducibility

The full analysis pipeline can be run end-to-end using a single script:

```r
source("scripts/run_all.R")
