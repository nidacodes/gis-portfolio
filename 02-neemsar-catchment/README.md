# 02 — Neemsar Catchment Delineation
## Gomti River Basin, Uttar Pradesh


<img width="3507" height="2480" alt="neemar_catchment" src="https://github.com/user-attachments/assets/1b4dfcd9-081e-4aba-b3ad-fa3d5c75e211" />
---

## What this map shows

A hydrological delineation map of the **Neemsar catchment** within the
**Gomti River Basin, Uttar Pradesh, India**.

The map shows:
- The **Neemsar sub-catchment** boundary — the upstream drainage area
  contributing flow to the Neemsar gauge site on the Gomti River
- The **Gomti River** linear path through the catchment
- The complete **stream and tributary network** draining into the Gomti
- The broader **Gomti River Catchment** as geographic context
- The **Neemsar Gauge Site** — the hydrological measurement station

The inset map shows the location of the study area within India.

---

## Why this map matters

The Gomti River is one of the major rivers of Uttar Pradesh, originating
in the Himalayan foothills and flowing ~960 km before joining the Ganga
at Varanasi. The Neemsar catchment represents the upper-to-middle
drainage basin of the Gomti, a hydrologically and ecologically
significant stretch of the river system.

Neemsar (Nimsar), in Sitapur district, is a historically significant
site on the Gomti — and the gauge station here provides critical
streamflow data for water resource management in UP.

---

## Data sources

| Source | Data used | Type |
|--------|-----------|------|
| **HydroSHEDS** (WWF / USGS) | Gomti River Basin boundary | Vector polygon |
| **HydroSHEDS + Google Earth Engine** | Neemsar sub-catchment delineation | Vector polygon |
| **National Water Data Portal** (Govt. of India) | River network · Gomti linear path | Vector line |
| **Natural Earth** | India country boundary (inset map) | Vector polygon |

---

## Workflow

1. Downloaded **Gomti River Basin** boundary from HydroSHEDS data portal
2. Extracted **Neemsar sub-catchment** from the Gomti basin using
   watershed delineation tools on **Google Earth Engine** —
   defining the pour point at the Neemsar gauge site
3. Downloaded **river network** from the National Water Data Portal
   (Government of India)
4. **Clipped** the full river network to the Neemsar catchment boundary
   in QGIS to extract streams and tributaries
5. **Extracted the Gomti linear path** from the clipped river network
   using attribute selection and dissolve
6. Added **Neemsar gauge point**, India inset map, and composed the
   final print layout in QGIS 3.44

---

## GIS skills demonstrated

- **Watershed delineation** on Google Earth Engine using HydroSHEDS
- **Multi-source data integration** — HydroSHEDS + National Water Data
  Portal + Natural Earth combined in one map
- **Vector clip and extract** operations in QGIS
- **Attribute-based feature selection** to isolate Gomti river path
- **Dissolve** to merge river segments into a continuous linear feature
- **River hierarchy symbology** — visual distinction between main river
  and tributary network
- **Inset map composition** in QGIS Print Layout
- **Professional hydrological map design** — clean white background,
  navy/blue colour scheme, journal-quality cartography
- **CRS management** — EPSG:4326 (data) → EPSG:32643 (UTM Zone 43N)

---

## Tools and software

| Tool | Purpose |
|------|---------|
| QGIS 3.44 | Main GIS platform — clipping, styling, layout |
| Google Earth Engine | Watershed delineation |
| HydroSHEDS Data Portal | Basin boundary download |
| National Water Data Portal | River network download |

---

## Coordinate reference system

| Stage | CRS | EPSG |
|-------|-----|------|
| Raw data | WGS84 geographic | 4326 |
| Analysis and map | WGS84 / UTM Zone 43N | 32643 |



---

## Part of my GIS learning portfolio

This is **Project 2 of 12** in my QGIS portfolio.
Learning path: QGIS → Python (GeoPandas, Rasterio) → R (sf, terra) → PostGIS.



---

*Data: HydroSHEDS (WWF/USGS) · National Water Data Portal (Govt. of India)*
*· Natural Earth · Made with QGIS 3.44 · Google Earth Engine*
*CRS: EPSG:32643 — WGS 84 / UTM Zone 43N*

