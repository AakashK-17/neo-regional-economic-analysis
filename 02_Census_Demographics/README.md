# Assignment 2 — Census Demographics

**"Who Lives and Works Here?"**

---

## What This Analyzes

This analysis builds a demographic profile of the seven-county NEO region using the Census Bureau's American Community Survey. It compares counties across five metrics — population, income, educational attainment, age distribution, and unemployment — and surfaces the structural tensions that matter most to Team NEO's talent strategy: where is education concentrated, where is income lagging, and which counties are winning or losing the 25–44 cohort that drives long-run regional vitality.

---

## Data Source

**U.S. Census Bureau — American Community Survey (ACS) 5-Year Estimates, 2023**  
- Survey years averaged: 2019–2023  
- Access method: Census Bureau Data API (`api.census.gov/data/2023/acs/acs5`)  
- Tables used:

| Table | Variable | Metric |
|-------|----------|--------|
| B01003 | `B01003_001E` | Total population |
| B19013 | `B19013_001E` | Median household income |
| B15003 | `_022E`–`_025E` / `_001E` | % with bachelor's degree or higher (pop 25+) |
| B01001 | `_011E`–`_014E`, `_035E`–`_038E` | % aged 25–44 (male + female, by 5-yr band) |
| B23025 | `_005E` / `_002E` | Unemployment rate (civilian labor force) |

---

## Tools

| Tool | Purpose |
|------|---------|
| Python 3.12 | Core language |
| requests | Live Census API fetch |
| pandas | Derived metric calculation, table formatting |
| matplotlib | Chart generation (comparison grid + bubble scatter) |

---

## Counties Analyzed

Cuyahoga · Summit · Stark · Lorain · Lake · Medina · Portage

All seven counties fall within the Cleveland-Akron-Canton Combined Statistical Area (CSA) and represent the primary geography of Team NEO's economic development mandate.

---

## Key Findings

- **Cuyahoga has the highest 25–44 concentration (26.5%) and the highest educational attainment (35.9% bach+) in the region — yet the lowest median household income ($62,823) and highest unemployment (6.9%).** Talent is present and staying, but the county is not generating the high-wage employment to match. This is the core retention tension: NEO's educated young workers are choosing to live in Cuyahoga but may not be finding commensurate careers.

- **Medina is the region's wealthiest county ($92,660 median income) with the lowest unemployment (3.0%) and highest educational attainment (36.2%)** — but its 25–44 share (23.4%) is the weakest among the inner-ring counties. Medina is attracting established, high-earning households, not young professionals. It is a success story for wealth accumulation but not for young talent attraction.

- **Stark County has the region's lowest educational attainment (25.0% bach+) but a low unemployment rate (3.9%)** — a profile consistent with a strong manufacturing economy that provides employment without requiring four-year degrees. This is not a failure; it is a different model that serves a different population.

- **Summit County offers the most balanced profile:** strong 25–44 share (25.7%), solid educational attainment (35.3%), income above the regional average ($71,016), and unemployment at 5.2%. Of all counties, Summit most closely resembles the target state Team NEO is working toward region-wide.

- **Regional averages (population-weighted):** Median income $68,904 | Bachelor's degree+ 33.0% | Ages 25–44: 25.2% | Unemployment: 5.5%

> **Note on unemployment rates:** ACS 5-year figures average survey responses over 2019–2023, which includes the 2020 COVID-era spike. These rates will be higher than BLS LAUS single-year 2023 estimates. The county-to-county comparison remains valid since the same averaging methodology applies across all geographies.

---

## Connection to Team NEO Strategy

These findings map directly onto two of Team NEO's declared strategic priorities:

**"Bend the Curve" (25–44 talent retention):** The regional 25–44 share of 25.2% is the benchmark. Cuyahoga is already above it at 26.5% — the challenge is not attracting this cohort but converting their presence into wage growth. Medina and Portage, at 23.4% and 22.9% respectively, represent the counties most at risk of aging out of the target demographic over the next decade without deliberate intervention.

**Vibrant Economy Index (VEI) — Income and Education correlation:** The scatter chart (Chart 2) makes the structural divide visible: Lake and Medina sit in the high-income quadrant regardless of education, while Cuyahoga — with the highest education — cannot convert that human capital into equivalent income. Closing that gap between educational attainment and median wages in Cuyahoga is, in concrete data terms, what "bending the curve" requires.

---

## Charts

| File | Description |
|------|-------------|
| `charts/neo_census_chart1_comparison.png` | Four-panel horizontal bar grid comparing all 7 counties across income, bachelor's degree %, ages 25–44 %, and unemployment rate — best county in each metric highlighted |
| `charts/neo_census_chart2_income_vs_education.png` | Bubble scatter plot of median income vs. bachelor's degree % by county; bubble size = population, color = % aged 25–44; reference lines mark regional averages |
