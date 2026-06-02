# Northeast Ohio Regional Research Portfolio

**Author:** Aakash Kunarapu
**Date:** June 2026

---

## Overview

This portfolio presents two independent data analysis assignments exploring the economic and demographic landscape of the Northeast Ohio (NEO) region. Each assignment draws from a primary federal data source, applies Python-based analysis and visualization, and surfaces findings relevant to Team NEO's core mission areas -- workforce development, talent attraction, and regional competitiveness. Together they demonstrate the ability to locate, clean, and interpret large public datasets and translate raw numbers into actionable regional insights.

The analyses are intentionally framed around Team NEO's strategic priorities, particularly the "Bend the Curve" initiative targeting the 25-44 age cohort and the Vibrant Economy Index (VEI) metrics. Where the data surfaces a tension -- such as Cuyahoga County's strong educational base paired with below-average incomes, or Medina County's high wealth but low young-worker retention -- that tension is called out explicitly, because understanding the gap between where NEO is and where it needs to be is the starting point for any effective economic development strategy.

---

## Assignments

| # | Assignment | Tools | Key Finding |
|---|-----------|-------|-------------|
| 1 | [BLS Workforce Analysis](01_BLS_Workforce_Analysis/) | Python, pandas, matplotlib, BLS QCEW | Healthcare is the region's largest employer (232K jobs) but pays only $1,194/week -- the "many jobs vs. good jobs" tension that defines NEO's wage challenge. |
| 2 | [Census Demographics](02_Census_Demographics/) | Python, requests, pandas, matplotlib, Census API | Cuyahoga has the region's highest 25-44 concentration (26.5%) and education level (35.9% bach+) yet the lowest median income ($62,823) -- talent is present but high-wage employment is not retaining it. |
| 3 | [County Maps](03_County_Maps/) | Python, GeoPandas, Folium, Census API | Interactive choropleth maps of unemployment, income, and the 25-44 prime workforce across all 7 NEO counties. |

---

## Data Sources

| Source | Dataset | Coverage | Access |
|--------|---------|----------|--------|
| U.S. Bureau of Labor Statistics | Quarterly Census of Employment and Wages (QCEW) -- Annual Averages, CSVs By Area | 2021-2024 | [bls.gov/cew](https://www.bls.gov/cew/) |
| U.S. Census Bureau | American Community Survey (ACS) 5-Year Estimates | 2023 (survey years 2019-2023) | [data.census.gov](https://data.census.gov) |
| U.S. Census Bureau | TIGER/Line Shapefiles 2023 | County boundaries | [Census TIGER](https://www2.census.gov/geo/tiger/TIGER2023/COUNTY/) |

---

## Repository Structure

```
TeamNEO_Research_Portfolio/
|-- README.md
|-- 01_BLS_Workforce_Analysis/
|   |-- neo_bls_analysis.ipynb
|   |-- README.md
|   `-- charts/
|       |-- neo_chart1_top_industries.png
|       |-- neo_chart2_employment_trend.png
|       `-- neo_chart3_wages.png
|-- 02_Census_Demographics/
|   |-- neo_census_analysis.ipynb
|   |-- README.md
|   `-- charts/
|       |-- neo_census_chart1_comparison.png
|       `-- neo_census_chart2_income_vs_education.png
`-- 03_County_Maps/
    |-- neo_maps.ipynb
    |-- README.md
    `-- maps/
        |-- neo_map1_unemployment.html
        |-- neo_map2_income.html
        |-- neo_map3_bend_the_curve.html
        |-- neo_map1_unemployment.png
        |-- neo_map2_income.png
        `-- neo_map3_bend_the_curve.png
```

> Raw BLS data folders (`2021_annual_by_area/` through `2024_annual_by_area/`) remain in `Downloads/` and are referenced by the BLS notebook. They are not tracked in this repository due to size.
