# Spatial Rainfall Analysis — Gomti Basin (1980–2023)

## Overview
Spatial analysis of 44 years of IMD rainfall data across 17 districts of the Gomti Basin, Uttar Pradesh. This project produces choropleth maps showing mean annual rainfall distribution and Mann-Kendall trend patterns across the basin.

## Maps Produced
- **Mean Annual Rainfall Map** — average annual rainfall (mm) per district (1980–2023)
- **Sen's Slope Map** — magnitude and direction of rainfall trend (mm/year) per district

## Key Findings
- Highest rainfall: Pilibhit (~1262 mm/year) — northern Terai region
- Lowest rainfall: Raibareili (~702 mm/year) — southern basin
- Significant decreasing trends detected in: Ayodhya, Unnao, Sitapur
- Only Shahjahanpur shows a significant increasing trend

## Data Source
- Indian Meteorological Department (IMD) gridded rainfall data
- Period: 1980–2023 | Unit: mm | Resolution: District-level

## Tools Used
- QGIS — spatial mapping and choropleth styling
- Python (pandas) — data preprocessing and mean annual rainfall calculation
- Mann-Kendall trend analysis — published separately (see linked paper)

## Part of Series
This is Project 4 of a 12-project QGIS learning series covering remote sensing, hydrology, urban planning, and environmental analysis.

## Related Publication
Mann-Kendall trend analysis of Gomti Basin rainfall — <img width="2480" height="3508" alt="monsoon" src="https://github.com/user-attachments/assets/67ab78aa-fac2-48f6-ad69-058372ba4061" />
<img width="2480" height="3508" alt="Layout" src="https://github.com/user-attachments/assets/11e87577-589e-427d-af35-8a6e31d29653" />

<img width="3507" height="2480" alt="rainfall_map" src="https://github.com/user-attachments/assets/b2456340-6c36-4c01-9c49-4bc5bdd4e6aa" />
(https://link.springer.com/article/10.1007/s00704-026-06062-9)
