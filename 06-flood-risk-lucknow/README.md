# 05 — Flood Risk Zone Map
## Lucknow City, Uttar Pradesh

<img width="3507" height="2480" alt="Flood_risk_zone" src="https://github.com/user-attachments/assets/6d843cf3-69bc-4644-bede-c985f230c6f8" />

---

## What this map shows

An **elevation-based flood risk assessment** of Lucknow city using
SRTM 30m Digital Elevation Model (DEM) data. The map classifies
the entire city into three flood risk zones based on terrain elevation
relative to the Gomti River floodplain.

### Key finding

> **The historic heart of Lucknow — Chowk, Qaiserbagh, Hazratganj,
> Marine Drive, and Mahanagar — lies within the high-risk flood zone
> along the Gomti River corridor.**

These are among the most densely populated and historically significant
neighbourhoods in Lucknow, making flood risk here a critical urban
planning and disaster management concern.

---

## Elevation analysis

| Risk zone | Elevation | Key areas |
|-----------|-----------|-----------|
| **High Risk** | 100 – 108m | Chowk, Qaiserbagh, Hazratganj, Marine Drive, Mahanagar, Gomti Nagar, Janeshwar Park |
| **Medium Risk** | 108 – 115m | Aliganj, Chinhat, Bahta, Bakhshi Ka Talab |
| **Low Risk** | 115 – 141m | Southern and western Lucknow |
| City elevation range | 100 – 141m | 41m total relief |
| DEM resolution | 30m | SRTM GL1 |

---

## Why elevation predicts flood risk

The Gomti River enters Lucknow from the northwest and flows
southeast — sitting at approximately 100–105m elevation.
Areas within 8m of river elevation (below 108m) are historically
inundated during monsoon flood events.

The southern half of Lucknow sits on higher ground and drains
through the Nagwa Nala, Kusaila Nala and Bakh Nala network —
visible in the map as the secondary drainage system.

The **Sai River** in the southwest flows at higher elevation than
the Gomti — explaining the absence of high-risk zones along
its corridor despite being a significant river.

---

## Data sources

| Source | Data used |
|--------|-----------|
| SRTM 30m (USGS) | Digital Elevation Model — elevation values per 30m pixel |
| National Water Data Portal (GoI) | River network — Gomti, Sai, Nalas |
| Own data | Lucknow city boundary shapefile |

---

## Workflow

1. Downloaded **SRTM 30m DEM** covering Lucknow using
   SRTM Downloader plugin in QGIS
2. **Reprojected DEM** from EPSG:4326 to EPSG:32643
   (WGS84 / UTM Zone 43N) using Raster → Warp (Reproject)
3. Used **Raster Calculator** to classify elevation into
   three flood risk classes:
   - Value 3 (High): elevation ≤ 108m
   - Value 2 (Medium): 108m < elevation ≤ 115m
   - Value 1 (Low): elevation > 115m
4. **Clipped flood risk raster** to Lucknow boundary using
   Raster → Extraction → Clip Raster by Mask Layer
5. Styled raster using **Paletted/Unique Values** renderer
   with yellow → orange → red colour scheme
6. Loaded **river network** from National Water Data Portal,
   clipped to Lucknow, styled by waterway type
   (Gomti bold navy, Sai medium blue, Nalas light blue)
7. Created **neighbourhood point layer** manually digitised
   in QGIS with key Lucknow localities for map context
8. Composed **print layout** with elevation analysis panel,
   legend, scale bar, north arrow, subtitle with key finding

---

## GIS concepts demonstrated

- **DEM raster loading and exploration** — pixel values as elevation
- **Raster reprojection** — Warp tool, EPSG:4326 → EPSG:32643
- **Raster Calculator** — conditional classification expression
- **Raster clipping** — Clip Raster by Mask Layer
- **Paletted/Unique Values renderer** — styling classified rasters
- **River hierarchy symbology** — categorised by waterway type
- **Manual digitising** — creating and labelling point features
- **Analytical subtitle** — communicating the key finding in one sentence
- **CRS management** — why raster must be in UTM before analysis

---

## Tools

| Tool | Purpose |
|------|---------|
| QGIS 3.44 | Main GIS platform |
| SRTM Downloader plugin | DEM download |
| Raster Calculator | Flood zone classification |
| National Water Data Portal | River network data |

---

## CRS

| Stage | CRS | EPSG |
|-------|-----|------|
| Raw SRTM DEM | WGS84 geographic | 4326 |
| Analysis and output | WGS84 / UTM Zone 43N | 32643 |

---

## Connection to Project 04

This is the **second part of a two-project urban analysis series
for Lucknow:**

- **Project 04** — Where are the green spaces?
  Only 18.2% of the city within 500m of a park
- **Project 05** — Where are the flood risks?
  Historic neighbourhoods along the Gomti at high risk

Together these two maps reveal a compounding urban vulnerability —
the areas with the least green infrastructure are also the areas
most exposed to flood risk. This is a research question worth
investigating further.



## Part of my GIS learning portfolio

This is **Project 5 of 12** in my QGIS portfolio.
Learning path: QGIS → Python (GeoPandas) → R (sf, terra) → PostGIS.

---

*Data: SRTM 30m (USGS) · National Water Data Portal (GoI)*
*Made with QGIS 3.44 · CRS: EPSG:32643 — WGS84 / UTM Zone 43N*

