# Assignment 1 — BLS Workforce Analysis

**"Who Works Here, and in What?"**

---

## What This Analyzes

This analysis profiles the private-sector workforce of the Cleveland-Akron-Canton Combined Statistical Area (CSA) using establishment-level payroll data from the Bureau of Labor Statistics. It answers three questions across the 2021–2024 period:

1. Which industries employ the most workers in NEO?
2. Which industries are growing or contracting?
3. Where does the pay gap sit — which sectors have scale but not wages?

---

## Data Source

**U.S. Bureau of Labor Statistics — Quarterly Census of Employment and Wages (QCEW)**  
- Product: Annual Averages, CSVs By Area  
- Coverage: 2021, 2022, 2023, 2024  
- Geography: Cleveland-Akron-Canton CSA, composed of three MSAs:
  - Cleveland-Elyria, OH MSA (C1746 / renamed C1741 in 2024)
  - Akron, OH MSA (C1042)
  - Canton-Massillon, OH MSA (C1594)
- Sector: Private ownership only (`own_code = 5`)
- Aggregation: MSA-level NAICS sector (`agglvl_code = 44`)
- Download: [bls.gov/cew/downloadable-data](https://www.bls.gov/cew/downloadable-data.htm)

---

## Tools

| Tool | Purpose |
|------|---------|
| Python 3.12 | Core language |
| pandas | Data loading, filtering, aggregation across 3 MSA files per year |
| matplotlib | Chart generation |
| os / pathlib | File path handling across year folders |

---

## Key Findings

- **Healthcare & Social Assistance is the dominant employer** at 232,183 average annual jobs in 2024 — and the fastest growing sector, up 11.2% since 2021. It is the backbone of the NEO labor market by volume.

- **Manufacturing is more resilient than the narrative suggests** — 187,064 jobs in 2024, up 5.8% from 2021, making it the second-largest private sector employer and defying the expectation of continued decline.

- **Administrative & Waste Services contracted** from an estimated peak down to 76,113 jobs — a likely signal of temp staffing pullback as employers shifted to direct hires or reduced headcount post-pandemic.

- **Management sector pays the highest average weekly wage at $2,272**, reflecting the concentration of corporate headquarters and holding company activity in the region.

- **Healthcare's wage-to-scale mismatch is the defining tension:** it employs the most workers but pays only $1,194/week on average — well below Finance & Insurance ($2,209), Management ($2,272), and Professional & Technical Services ($1,898). NEO has the jobs; it does not yet have the compensation to match.

- **Transportation & Warehousing grew 83.6%** from 2021–2024, the fastest of any sector — likely driven by logistics infrastructure investment around the I-77/I-76 corridor and e-commerce fulfillment expansion.

---

## Data Gap — 2024 Cleveland MSA Renaming

The 2024 BLS data release renamed and renumbered the Cleveland-Elyria, OH MSA:

> `C1746 Cleveland-Elyria, OH MSA` → `C1741 Cleveland, OH MSA`

This is a standard BLS delineation update reflecting revised OMB metropolitan area definitions. The notebook detects this automatically: it tries `C1746` first, then falls back to `C1741`, then the CSA-level file, then skips — logging exactly which source was used for each year. The 2024 data used `C1741` successfully with no gap in coverage.

---

## Charts

| File | Description |
|------|-------------|
| `charts/neo_chart1_top_industries.png` | Horizontal bar chart of the top 10 private-sector industries by average annual employment in 2024, with value labels in thousands |
| `charts/neo_chart2_employment_trend.png` | Line chart tracking employment from 2021–2024 for the top 5 industries, showing trajectory and relative scale |
| `charts/neo_chart3_wages.png` | Horizontal bar chart of the top 10 industries by average weekly wage, color-coded by wage tier |
