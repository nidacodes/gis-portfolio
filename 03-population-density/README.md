# 03 — India Population Density Map
## State-level Choropleth · Census 2011

<img width="3507" height="2480" alt="Pop_density" src="https://github.com/user-attachments/assets/79342632-7e4e-4f58-b805-310d4e470f3c" />


---

## What this map shows

A choropleth map of **India showing population density by state**,
calculated from Census 2011 data. Darker red indicates higher
population density (people per km²), lighter yellow indicates
lower density.

### Key findings

| State | Density (per km²) | Category |
|-------|-------------------|----------|
| Bihar | ~1,106 | Highest |
| West Bengal | ~1,028 | Very High |
| Uttar Pradesh | ~829 | Very High |
| Kerala | ~860 | Very High |
| Rajasthan | ~201 | Low |
| Arunachal Pradesh | ~17 | Very Low |
| Ladakh | ~4.64 | Lowest in India |

---

## Data sources

| Source | Data used |
|--------|-----------|
| Census of India 2011 | State-level population totals |
| GADM Administrative Boundaries | India state boundary shapefile |

---

## Workflow

1. Loaded India state boundary shapefile (GADM) into QGIS
2. Prepared Census 2011 population CSV with state name,
   population, and area columns
3. **Joined CSV to shapefile** using state name as the
   common field — resolved name mismatch issues between
   datasets (case differences, special characters)
4. Used **Field Calculator** to compute population density:
   `population ÷ area_km2`
5. Applied **Jenks Natural Breaks** classification into
   5 classes — appropriate for skewed population data
6. Styled with **YlOrRd colour ramp** (yellow → orange → red)
7. Added J&K and Ladakh separately following the 2019
   bifurcation into two union territories
8. Composed print layout with title, legend, scale bar,
   north arrow, and data credit

---

## GIS concepts demonstrated

- **Attribute join** — linking non-spatial CSV data to
  spatial shapefile using a common field
- **Field Calculator** — computing derived values
  (density = population ÷ area)
- **Graduated symbology** — classifying continuous numeric
  data into colour ranges
- **Jenks Natural Breaks** — optimal classification method
  for skewed data distributions
- **Real data cleaning** — resolving name mismatches between
  two independently sourced datasets
- **Legend design** — meaningful class labels for a
  choropleth map
- **CRS management** — EPSG:4326 data, EPSG:32643 analysis

---

## Tools

| Tool | Purpose |
|------|---------|
| QGIS 3.44 | Main GIS platform |
| Excel | CSV preparation and UPPER() formula for name matching |

---

## Data challenges encountered

The most educational part of this project was not the mapping
itself but the data integration:

- State names in the shapefile were in **ALL CAPS** while
  the CSV used Title Case — fixed using Excel `UPPER()` formula
- Shapefile had **40 rows** (includes union territories)
  while CSV had 30 states — NULL values for UTs handled by
  adding J&K and Ladakh separately
- J&K bifurcation in 2019 meant the shapefile shows two
  separate polygons — both required individual population
  and area values

These are real-world GIS data challenges — the kind
encountered in every professional project.

---

## What I would improve next

- Use district-level data (518 districts) for finer spatial detail
- Add state name labels for major states
- Include an inset map showing India in South Asian context
- Add a histogram showing the distribution of density values
- Use 2021 Census data when officially released

---

## Part of my GIS learning portfolio

This is **Project 3 of 12** in my QGIS portfolio.
Learning path: QGIS → Python (GeoPandas) → R (sf, terra) → PostGIS.



---

*Data: Census of India 2011 · GADM Administrative Boundaries*
*Made with QGIS 3.44 · CRS: EPSG:32643 — WGS84 / UTM Zone 43N*

