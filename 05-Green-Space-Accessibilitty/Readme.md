# 05 — Green Space Accessibility Analysis
## Lucknow, Uttar Pradesh


---

## What this map shows

A spatial accessibility analysis of **green spaces in Lucknow, Uttar Pradesh**
— mapping which parts of the city fall within walking distance of a park,
garden, playground, or sports ground.<img width="3507" height="2480" alt="Lucknow_green_space" src="https://github.com/user-attachments/assets/7a936fe9-9fdb-49f3-a90d-24b52226cb24" />


### Key finding

> **Only 18.2% of Lucknow lies within 500m of a green space.**
> For a city of 3.2 million people, this represents a significant
> urban planning and public health gap.

| Walking zone | Area covered | % of city |
|---|---|---|
| Within 500m | 178.79 km² | **18.2%** |
| Within 1000m | 344.69 km² | **35.1%** |
| City total | 982.37 km² | 100% |

---

## What the map reveals

Green spaces in Lucknow are heavily concentrated in the **eastern half**
of the city — around the Gomti Riverfront, Janeshwar Mishra Park,
and the older established neighbourhoods.

The **western half** — covering large residential areas — has almost
no green space coverage within walking distance. This spatial inequality
in access to green infrastructure is clearly visible in the map.

---

## Data sources

| Source | Data used |
|--------|-----------|
| OpenStreetMap via QuickOSM | Parks, gardens, playgrounds, sports grounds |
| Own data | Lucknow city boundary shapefile |

### OSM queries used
- `leisure = park`
- `leisure = garden`
- `leisure = playground`
- `leisure = pitch`

---

## Workflow

1. Downloaded all green space features from OpenStreetMap
   using the **QuickOSM plugin** with four key/value queries
2. Filtered to **polygon geometries only** — removed point
   and line features not suitable for buffer analysis
3. Merged all four green space layers into one using
   **Merge Vector Layers**
4. Verified CRS — both layers in **EPSG:32643**
   (WGS84 / UTM Zone 43N) — essential for metre-based buffers
5. Ran **Buffer** at 500m and 1000m with dissolve ON
   — merges overlapping buffers into single coverage zones
6. **Clipped** both buffers to Lucknow city boundary
7. Used **Field Calculator** (`$area / 1000000`) to calculate
   area in km² for city boundary and both buffer layers
8. Computed coverage percentage manually:
   buffer area ÷ city area × 100
9. Styled layers with green hierarchy and composed
   print layout in QGIS 3.44

---

## GIS concepts demonstrated

- **Buffer analysis** — fixed distance buffers at 500m and 1000m
- **Why CRS matters for buffer** — metre-based distances require
  a projected CRS (EPSG:32643), not geographic degrees (EPSG:4326)
- **Dissolve** — merging overlapping buffer polygons into
  single continuous coverage zones
- **Clip** — trimming buffers to city boundary extent
- **Field Calculator** — `$area / 1000000` for area in km²
- **Multi-layer OSM data download** — four QuickOSM queries
  combined into one analysis layer
- **Coverage percentage calculation** — spatial arithmetic
  from field calculator outputs
- **Green hierarchy symbology** — dark green (actual spaces)
  to light green (walking zones) with transparency

---

## Tools

| Tool | Purpose |
|------|---------|
| QGIS 3.44 | Main GIS platform |
| QuickOSM plugin | Downloading OSM green space data |
| Field Calculator | Area calculation and coverage percentage |

---

## CRS

| Stage | CRS | EPSG | Reason |
|-------|-----|------|--------|
| Raw OSM data | WGS84 geographic | 4326 | Default OSM delivery |
| Analysis and buffers | WGS84 / UTM Zone 43N | 32643 | Metre-based distance accuracy |

**Key lesson:** Running a 500m buffer in EPSG:4326 would mean
500 degrees — wrapping around Earth multiple times.
Always reproject to UTM before any distance-based operation.

---


---

## Part of my GIS learning portfolio

This is **Project 4 of 12** in my QGIS portfolio.
Learning path: QGIS → Python (GeoPandas) → R (sf, terra) → PostGIS.

**Next project:** Flood Risk Zone Mapping — SRTM DEM,
Raster Calculator, raster-vector overlay.

---

*Data: © OpenStreetMap contributors · Made with QGIS 3.44*
*CRS: EPSG:32643 — WGS84 / UTM Zone 43N*



