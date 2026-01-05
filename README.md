# Milwaukee County Equity Analysis Using Census Microdata (PUMS)

## Overview

This repository contains a fully reproducible equity and needs analysis of poverty and housing cost burden in Milwaukee County, using the American Community Survey (ACS) Public Use Microdata Sample (PUMS). It demonstrates how Census microdata can be used to quantify compounding disadvantage across overlapping characteristics (race/ethnicity, disability status, nativity) in ways that are not possible with standard pre-tabulated ACS tables.

All data processing, weighting, analysis, and visualization steps are automated in R. The complete codebase is included to support transparency and reproducibility.

## Full Report (PDF)
📄 **Milwaukee County Equity Analysis Report:**  
[Download the full report (PDF)](https://github.com/DemoAnalytics/mke_pums_equity/tree/main/report)


---

## Why this matters (practical applications)

Nonprofits, local governments, and consulting firms frequently rely on Census data to support:
<ul>
<li>equity-focused planning and program design</li>

<li>grant applications, needs statements, and reporting</li>

<li>program targeting and service area prioritization</li>

<li>evaluation and performance measurement</li>
</ul>
While standard ACS summary tables are appropriate for many uses, they are limited when the research question involves multiple interacting characteristics (e.g., race × disability × nativity). This project shows how microdata can produce policy-relevant estimates that reveal disparities hidden in standard tables.

---

## Key Questions answered

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

## Geographic methodology (PUMA → County estimation)

Because ACS microdata is released at the Public Use Microdata Area (PUMA) level (for privacy), it does not align perfectly with county boundaries.

To approximate Milwaukee County estimates, this project applies official geographic allocation factors from the Missouri Census Data Center. These factors represent the share of each PUMA’s population located within Milwaukee County.

Survey weights are adjusted using these allocation factors to produce Milwaukee County–specific estimates.

Interpretation note: Results should be interpreted as statistically robust estimates intended to identify patterns and disparities—not as exact administrative counts.
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
## How to use / adapt this workflow
This repository is structured to support adaptation to other counties or metro areas by updating:

- the PUMA geography correspondence inputs

- the target county or region definition

- the population group and outcome specifications

---
## Tools

- R: tidyverse, survey, srvyr, tidycensus, sf

- Outputs can be mapped and styled in QGIS for client-ready figures
---

## Contact

If you’re a public agency, nonprofit, or consulting firm that needs demographic and equity analysis to support planning or grant work, feel free to reach out:
Chuck Brown — demo-analytics.com

