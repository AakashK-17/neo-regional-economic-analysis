# Assignment 3 — NEO County Economic Maps

**Interactive choropleth maps of Northeast Ohio's economic and demographic landscape**

---

## Tools

| Tool | Purpose |
|------|---------|
| Python 3.12 | Core language |
| GeoPandas | County boundary shapefiles + spatial merge |
| Folium | Interactive HTML choropleth maps |
| Matplotlib | Static PNG exports |
| requests | Live Census API fetch |
| Census TIGER | County boundary geometries |

---

## Data Sources

| Source | Dataset | Access |
|--------|---------|--------|
| U.S. Census Bureau -- ACS 5-Year Estimates, 2024 | Income, education, age, unemployment | Census API `api.census.gov/data/2024/acs/acs5` |
| U.S. Census Bureau -- TIGER/Line Shapefiles 2023 | County boundaries (WGS-84) | `www2.census.gov/geo/tiger/TIGER2023/COUNTY/` |

Counties: **Cuyahoga · Summit · Stark · Lorain · Lake · Medina · Portage**

---

## Maps

### Map 1 -- Unemployment Rate
**`maps/neo_map1_unemployment.html`** *(interactive)* | **`maps/neo_map1_unemployment.png`** *(static)*

Choropleth on a white-to-red scale where darker red = higher unemployment. Each county has a click popup showing the rate and how far it sits above or below the regional average. Best-performing county (Medina, 2.9%) and worst-performing (Cuyahoga, 6.6%) are marked. The 3.7 percentage point spread across a single metro area reflects two parallel economic tracks: a resilient outer ring and a struggling urban core.

---

### Map 2 -- Median Household Income
**`maps/neo_map2_income.html`** *(interactive)* | **`maps/neo_map2_income.png`** *(static)*

Choropleth on a white-to-dark-blue scale. Each popup shows income and dollar deviation from the regional average ($70,762). Medina (highest, $94,968) and Cuyahoga (lowest, $64,468) are highlighted with distinct markers. The $30,500 income gap between these two counties -- which share a border -- is the sharpest illustration of NEO's income stratification problem.

---

### Map 3 -- The "Bend the Curve" Map
**`maps/neo_map3_bend_the_curve.html`** *(interactive)* | **`maps/neo_map3_bend_the_curve.png`** *(static)*

Red-to-green diverging choropleth anchored at the regional average 25-44 share (25.4%). Green counties are above average on the prime workforce metric; red counties are below. Each popup shows all three talent metrics together: age share, bachelor's degree %, and median income. A dashed circle and callout highlight Cuyahoga as the region's highest-talent, lowest-income county -- the core tension in Team NEO's retention challenge.

---

## Key Insight -- The Cuyahoga Paradox

Cuyahoga County is simultaneously NEO's greatest asset and its most urgent challenge:

- **Highest prime workforce share:** 26.8% aged 25-44 (regional avg: 25.4%)
- **Highest educational attainment:** 36.5% with bachelor's degree or higher (now leads the region)
- **Lowest median income:** $64,468 -- $30,500 below Medina, $6,294 below regional avg
- **Highest unemployment:** 6.6% (regional avg: ~4.6%)

The data does not describe a talent attraction problem. It describes a **job quality and wage growth problem**. The young, educated workforce is already in Cuyahoga. The missing piece is the density of high-wage employers to convert that human capital into household income -- which is precisely the economic development mandate at the heart of Team NEO's Bend the Curve initiative.

> **Note (ACS 2024 update):** Cuyahoga overtook Medina to become the region's most educated county (36.5% vs 36.2% bach+). The income gap widened slightly -- Medina grew to $94,968 while Cuyahoga reached $64,468. The core paradox sharpens: more education, still the lowest wages.
