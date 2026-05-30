# 08 — Spectral Indices Analysis
## Lucknow City, Uttar Pradesh · Sentinel-2 · 16 February 2025

<img width="4960" height="3507" alt="Indices" src="https://github.com/user-attachments/assets/2c912adb-46ba-4091-a939-68c610d87b6c" />

---

## What this map shows

An **8-panel spectral indices dashboard** of Lucknow City derived
from Sentinel-2 MSI Level-2A imagery (16 February 2025, 0% cloud cover).
Each panel reveals a different biophysical characteristic of the urban
landscape using specific band combinations.

---

## Indices computed

| Index | Formula | What it reveals |
|-------|---------|-----------------|
| **FCC** | B08=R, B04=G, B03=B | False colour composite — vegetation pink, urban cyan |
| **NDVI** | (B08−B04)/(B08+B04) | Vegetation health — green = healthy, red = sparse |
| **NDWI** | (B03−B08)/(B03+B08) | Water bodies — blue = water present |
| **NDBI** | (B11−B08)/(B11+B08) | Built-up areas — red = dense urban |
| **NDMI** | (B08−B11)/(B08+B11) | Moisture content — blue = high moisture |
| **BSI** | ((B11+B04)−(B08+B02))/((B11+B04)+(B08+B02)) | Bare soil — brown = exposed soil |
| **GNDVI** | (B08−B03)/(B08+B03) | Green vegetation — more sensitive than NDVI |
| **AWEIsh** | B02+2.5×B03−1.5×(B08+B11)−0.25×B12 | Water extraction with shadow correction |

---

## Key findings from the indices

**NDVI (max: 0.69)** — Low vegetation dominates most of Lucknow city shown by red/orange across the urban core. Healthy vegetation (green) appears only in small scattered patches — consistent with Project 04 findings showing only 18.2% of the city within 500m of a green space. February dry season further reduces vegetation vigour across the city.



**NDBI (max: 0.39)** — High built-up density across the central
and northern city — Chowk, Hazratganj, Mahanagar corridor clearly
visible as high NDBI zones, consistent with Project 06 flood risk
findings showing these as high-risk areas.

**NDWI** — Gomti River corridor visible as the primary water feature.
Limited open water in February consistent with dry season conditions.

**BSI** — Bare soil concentrated in the southern and western
periphery — areas of active construction and agricultural fringe.

**AWEIsh** — Shadow-corrected water extraction confirming Gomti
River and associated water bodies. February dry season limits
surface water extent across the city.

---

## Data

| Item | Detail |
|------|--------|
| Satellite | Sentinel-2C MSI |
| Product | Level-2A (atmospherically corrected) |
| Date | 16 February 2025 |
| Cloud cover | 0% |
| Tile | T44RMQ |
| Resolution | 10m (B02,B03,B04,B08) · 20m (B11,B12) |
| Download method | Sentinel-2 plugin in QGIS |

---

## Bands used

| Band | Name | Resolution | Used in |
|------|------|-----------|---------|
| B02 | Blue | 10m | FCC, BSI, AWEIsh |
| B03 | Green | 10m | FCC, NDWI, GNDVI, AWEIsh |
| B04 | Red | 10m | FCC, NDVI, BSI |
| B08 | NIR | 10m | All indices |
| B11 | SWIR-1 | 20m | NDBI, NDMI, BSI, AWEIsh |
| B12 | SWIR-2 | 20m | AWEIsh |

---

## Workflow

1. Searched and downloaded Sentinel-2 imagery using
   **Sentinel-2 plugin in QGIS** — selected tile T44RMQ,
   16 February 2025, 0% cloud cover
2. Selected bands B02, B03, B04, B08, B11, B12 and
   indices NDVI, NDWI, NDBI, NDMI, BSI, GNDVI
   for automatic calculation during download
3. Clipped all bands and index rasters to
   **Lucknow city boundary** using Raster → Clip by Mask Layer
4. Calculated **AWEIsh** manually using Raster Calculator
5. Styled each index with appropriate colour ramp —
   RdYlGn (NDVI/GNDVI), Blues (NDWI/NDMI/AWEIsh),
   OrRd (NDBI), YlOrBr (BSI)
6. Built FCC using B08=Red, B04=Green, B03=Blue
   multiband composite
7. Composed **8-panel print layout** in QGIS 3.44
   with individual legends per panel
8. Exported at **300 DPI** — A3 landscape

---

## GIS and remote sensing skills demonstrated

- **Sentinel-2 data acquisition** — plugin-based download,
  tile selection, cloud cover filtering
- **Multispectral band analysis** — understanding band
  combinations and their physical meaning
- **Raster Calculator** — multi-band formula computation
  including AWEIsh shadow-corrected water extraction
- **Raster clipping** — Clip Raster by Mask Layer
- **Index classification and styling** — appropriate colour
  ramps per index type
- **False Colour Composite** — NIR-Red-Green band combination
- **Multi-panel print layout** — 8 maps with individual
  legends in one A3 composition
- **Storage management** — handling large satellite data
  on secondary drive to avoid system drive overflow
- **CRS management** — EPSG:32644 (UTM Zone 44N)
  matching Sentinel-2 tile projection

---

## Tools

| Tool | Purpose |
|------|---------|
| QGIS 3.44 | Main platform — clipping, styling, layout |
| Sentinel-2 plugin | Imagery download and index calculation |
| Raster Calculator | AWEIsh manual computation |
| Copernicus Dataspace | Sentinel-2 data source |

---

## Connection to Lucknow project series

This is the **fourth project in the Lucknow urban analysis series:**

| Project | What it analysed |
|---------|-----------------|
| Project 05 | Green space accessibility — 18.2% within 500m |
| Project 06 | Flood risk — Gomti corridor high risk zone |
| Project 07 | LULC mapping — ESRI 10m land cover |
| **Project 08** | **Spectral indices — 8 biophysical parameters** |

Together these four projects build a comprehensive
spatial understanding of Lucknow from multiple
remote sensing and GIS perspectives.





---

*Data: Sentinel-2 ESA/Copernicus · 16 February 2025*
*Made with QGIS 3.44 · CRS: EPSG:32644 — WGS84/UTM Zone 44N*
