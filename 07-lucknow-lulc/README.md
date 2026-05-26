# Project 07 — Lucknow Land Use Land Cover Map

![QGIS](https://img.shields.io/badge/QGIS-3.34-green) ![Data](https://img.shields.io/badge/Data-ESRI%20LULC%202024-blue) ![Resolution](https://img.shields.io/badge/Resolution-10m-orange)

## Overview
A landcover map of Lucknow district, Uttar Pradesh, India.
Built using ESRI 10m LULC 2024 data with a hillshade layer
for terrain depth. Part of a 12-project QGIS learning series.

---<img width="3507" height="2480" alt="Lucknow LULC" src="https://github.com/user-attachments/assets/13079710-6a13-40ba-bae6-119e11086d0d" />


## Data Sources
| Dataset | Source | Resolution |
|---|---|---|
| Land Use Land Cover | ESRI LULC 2024 | 10m |
| Digital Elevation Model | CGIAR-SRTM | 30m |
| District Boundary | GADM Level 3 | Vector |

---

## Landcover Classes
| Class | Colour |
|---|---|
| Built-up Area | Red |
| Crops | Yellow |
| Trees | Dark Green |
| Water | Blue |
| Rangeland | Orange |
| Bare Ground | Tan |
| Flooded Vegetation | Light Green |
| Snow / Ice | White |

---

## Workflow
1. Download ESRI LULC 2024 GeoTIFF for Lucknow area
2. Download SRTM DEM tiles and merge
3. Clip both rasters to Lucknow district boundary
4. Style landcover using Paletted/Unique Values
5. Generate hillshade (Z Factor: 5, Azimuth: 315°)
6. Blend hillshade over landcover (Multiply, 65% opacity)
7. Compose final map in Print Layout

---

## Key Challenge
Layers were in different coordinate reference systems —
some in projected metres (UTM Zone 44N) and others in
geographic decimal degrees (WGS 84). Resolved by
reprojecting all layers to a common CRS before clipping
and analysis, ensuring spatial accuracy and correct
scale in the final output.

---

## Tools Used
- QGIS 3.34
- Raster → Analysis → Hillshade
- Raster → Extraction → Clip by Mask Layer
- Layer blending (Multiply mode)
- QGIS Print Layout

---
