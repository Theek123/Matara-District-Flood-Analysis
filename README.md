# Matara-District-Flood-Analysis
This project analyzes the impact of flooding in Matara District, Sri Lanka during September–October 2023 using Sentinel-1 Synthetic Aperture Radar (SAR) imagery.
## Overview

This project analyzes the **impact of flooding in Matara District, Sri Lanka** during September–October 2023 using **Sentinel-1 Synthetic Aperture Radar (SAR) imagery**.  
The study compares **pre-flood** (26th September 2023) and **post-flood** (8th October 2023) conditions to assess the **spatial extent of flooding**, particularly in agricultural areas, settlements, and infrastructure.  

SAR-based flood mapping is especially useful because it can **penetrate clouds and rainfall**, providing reliable flood monitoring even under extreme weather conditions.

---

## Study Area

<p align="center">
  <img src="Images/Study_Area.jpg" width="450">
  <br><em>Study Area, Matara District</em>
</p>
Matara District is located in the Southern Province of Sri Lanka, covering an area of approximately 1,301 km². It lies along the southern coastline of the island, bounded by the Indian Ocean to the south, and is characterized by a combination of coastal lowlands, riverine floodplains, and gently undulating inland terrain. According to the 2012 census, the district has a population of approximately 804,000, with a relatively high population density, particularly in urban and semi-urban areas.

A defining geographical feature of the district is the Nilwala River, which originates in the central highlands and flows southward through Matara before discharging into the Indian Ocean. The river basin forms extensive alluvial plains, which are intensively used for paddy cultivation and other agricultural activities. These low-lying areas, while agriculturally productive, are highly susceptible to seasonal flooding, especially during periods of prolonged rainfall.

Climatically, Matara falls within the wet zone of Sri Lanka, receiving substantial rainfall primarily from the Southwest Monsoon (May to September) and the Second Inter-Monsoon (October to November). The district’s proximity to the ocean enhances moisture availability, often leading to intense and continuous rainfall events. These climatic conditions, combined with relatively flat terrain and poor drainage in certain areas, significantly increase the district’s vulnerability to riverine floods, surface water accumulation, and occasional landslides in inland regions.

In terms of infrastructure, the district is traversed by major transportation routes, including the Southern Expressway (E001), which plays a crucial role in regional connectivity. However, these infrastructure networks are frequently affected during extreme weather events, highlighting the importance of effective flood monitoring and management.

Overall, the interaction between hydrological systems (Nilwala River), climatic patterns (monsoonal rainfall), and land use (agriculture and settlements) makes Matara District a highly flood-prone region, providing a suitable case study for analyzing flood dynamics using remote sensing and GIS techniques.

---

## Data Used

| Data | Source | Description |
|------|--------|-------------|
| Sentinel-1 SAR | [Copernicus Open Access Hub](https://browser.dataspace.copernicus.eu) | Pre-flood (26-Sep-2023) and Post-flood (08-Oct-2023) imagery |
| DEM | Generated from Sentinel-1 product| Used for terrain correction and flood mapping |
| Matara District boundary | (https://diva-gis.org/data.html) | Clipping flood extent to study area |
| Road network | OpenStreetMap / Local GIS sources | For infrastructure impact assessment |

> **Note:** Large SAR products are not included in this repository. Download links is provided here.

---
## Tools & Software

- **SNAP (ESA Sentinel Application Platform)** – SAR pre-processing and water extraction  
- **ArcGIS Pro** – Mapping, spatial analysis, attribute calculation  
- **Other GIS datasets** – DEMs, shapefiles for roads and administrative boundaries  
---
## Methodology

### 1. SAR Pre-processing (in SNAP)

1. **Import Sentinel-1 images** (pre- and post-flood)  
2. **Thermal Noise Removal** – Reduce signal noise from thermal effects  
3. **Orbit File Correction** – Improve geometric accuracy using precise satellite orbit data  
4. **Radiometric Calibration** – Convert backscatter values to comparable measurements (Gamma Nought)  
5. **Terrain Correction (Range-Doppler)** – Align SAR images to real-world coordinates using DEM  
6. **Water Extraction** – Identify flooded areas using thresholding on VV/VH polarizations  
7. **Export processed water layer** – GeoTIFF format for use in ArcGIS  

### 2. GIS Analysis (in ArcGIS Pro)

1. **Clip water layer** to Matara District boundary  
2. **Dissolve water and land polygons** for better visualization  
3. **Calculate water-covered area and percentage** pre- and post-flood  
4. **Overlay roads and settlements** to assess infrastructure impact  
5. **Map flood extent in agricultural lands** (particularly paddy fields along Nilwala River)  
6. **Compare pre- and post-flood maps** to quantify inundation and land cover changes  

---
## Results

| Metric | Pre-Flood (26-Sep-2023) | Post-Flood (08-Oct-2023) | Change |
|--------|------------------------|--------------------------|--------|
| Water-covered area | 13.15 km² (1.01%) | 40.24 km² (3.09%) | +27.09 km² (+206%) |
| Land area | 1,288.15 km² (98.99%) | 1,261.06 km² (96.91%) | -27.09 km² (-2.1%) |

**Observations:**

- Flooding concentrated in **southern and central parts** of Matara District
<p align="center">
  <img src="Images/Pre-Post.jpg" width="450">
  <br><em>Pre and Post flood maps</em>
</p>

- Significant inundation along Nilwala river basin.
- Infrastructure impact: Southern Expressway sections were impassable due to flooding.
- Agricultural impact: Large paddy fields in Thihagoda, Malimbada, Athuraliya, and Akuressa submerged, likely causing crop damage and economic loss.
<p align="center">
  <img src="Images/DS_Areas.jpeg" width="450">
  <br><em>Flood and Divisional Secretariat Areas</em>
</p>
---

Author : Theekshana Pathirana
BSc. in Geographical Information Science



