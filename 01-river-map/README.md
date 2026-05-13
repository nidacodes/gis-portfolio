<img width="3507" height="2480" alt="up_RIVER" src="https://github.com/user-attachments/assets/0f7e71bc-76c5-4d63-b4fc-b50cccfefa94" />
# 01 — Uttar Pradesh River Network

![Uttar Pradesh River Network Map](up_river_network.png)

---

## What this map shows

A hierarchical river and waterway network map of **Uttar Pradesh**, India —
mapped from OpenStreetMap data using QGIS.

The map visualises the drainage pattern of UP's major river systems:

| River | Significance |
|-------|-------------|
| **Ganga** | Primary river, flows east across the Gangetic Plain |
| **Yamuna** | Western boundary, tributary of Ganga at Prayagraj |
| **Ghaghra (Saryu)** | Largest northern tributary, originates in Nepal |
| **Gomti** | Flows through Lucknow, joins Ganga at Varanasi |
| **Betwa** | Southern tributary, flows through Bundelkhand |
| **Son** | Southernmost major river, joins Ganga in Bihar |
| **Tamsa (Tons)** | Eastern river system, drains into Ganga |
| **Kali Nadi, Sharda** | Northern tributaries from the Himalayas |

Rivers are styled by hierarchy — **major rivers** (thick, dark blue) are
visually distinct from **streams** (thin, light blue) — so the drainage
pattern reads clearly at state scale.

---

## Skills demonstrated

- **QuickOSM plugin** — downloading OSM waterway data by key/value query
- **Categorised symbology** — styling line features by `waterway` type
  with visual hierarchy (width + colour vary by feature type)
- **Rule-based labelling** — labelling only `waterway = 'river'` features
  with curved placement following river geometry
- **Label rendering** — merge connected lines, suppress short features,
  minimum length filter to remove illegible labels
- **CRS management** — data in EPSG:4326, project in EPSG:32643
  (WGS84 / UTM Zone 43N) for accurate spatial work in North India
- **Print layout** — title, subtitle, scale bar, north arrow,
  legend, data attribution, 300 DPI export

---

## Tools and data

| Item | Detail |
|------|--------|
| Software | QGIS 3.44 |
| Data source | OpenStreetMap contributors |
| Download method | QuickOSM plugin — key: `waterway` |
| Study area | Uttar Pradesh state boundary |
| Data CRS | EPSG:4326 (WGS84 geographic) |
| Project CRS | EPSG:32643 (WGS84 / UTM Zone 43N) |
| Export | 300 DPI PNG, A3 landscape |

---



---

## About this portfolio


This is **Project 1 of 12** in my QGIS learning portfolio.
Learning path: QGIS → Python (GeoPandas, Rasterio) → R (sf, terra) → PostGIS.

**Next project:** Population density choropleth of India by district.

---

*Data: © OpenStreetMap contributors · Made with QGIS 3.44*
*CRS: EPSG:32643 — WGS 84 / UTM Zone 43N*

