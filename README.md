# Lagos State Vegetation Greenness Monitoring (2019–2025)

**A cloud-based remote sensing and geospatial analysis of vegetation greenness across the 20 Local Government Areas of Lagos State, Nigeria.**

## 1. Project Overview

This project investigates temporal variations in vegetation greenness across Lagos State, Nigeria, between 2019 and 2025 using Sentinel-2 satellite imagery.

The analysis applies the Normalized Difference Vegetation Index (NDVI) and Enhanced Vegetation Index (EVI) to examine vegetation greenness patterns at state and Local Government Area (LGA) levels.

Google Earth Engine was used for satellite image processing, cloud masking, vegetation index computation and annual composite generation. Python was used through Google Colab for statistical analysis, data visualisation and animation production.

The project provides spatial and temporal evidence that can contribute to vegetation monitoring and environmental assessment.

## 2. Research Objectives

The specific objectives were to:

1. Estimate annual vegetation greenness using NDVI and EVI.
2. Examine temporal variations in vegetation indices between 2019 and 2025.
3. Compare vegetation greenness patterns across Lagos State's 20 LGAs.
4. Identify spatial differences in vegetation index trends across administrative areas.
5. Develop visual outputs to communicate the observed patterns and changes.

## 3. Study Area

The study covers Lagos State, southwestern Nigeria, using its 20 Local Government Areas as administrative reporting units.

The LGA boundaries were obtained from the FAO Global Administrative Unit Layers (GAUL 2015), Level 2 dataset, filtered to Lagos State, Nigeria.

The administrative boundaries provide a consistent framework for summarising and comparing vegetation index values across the study area.

## 4. Data and Sources

| Dataset | Source | Application |
|---|---|---|
| Sentinel-2 Surface Reflectance Harmonized | Google Earth Engine | Satellite imagery |
| GAUL 2015 Level 2 | FAO | LGA boundaries |
| Sentinel-2 Scene Classification Layer (SCL) | Sentinel-2 | Cloud and shadow masking |

**Satellite imagery specifications**

- Satellite: Sentinel-2
- Earth Engine collection: `COPERNICUS/S2_SR_HARMONIZED`
- Spatial resolution: 10 metres for the bands used
- Spectral bands: Blue (B2), Red (B4), Near Infrared (B8)
- Study period: 2019–2025
- Seasonal window: May–October
- Temporal compositing: Annual median composites

The year 2018 was excluded because the available imagery did not provide sufficient coverage during the selected seasonal window.

## 5. Methodology

### 5.1 Image Collection and Preprocessing

Sentinel-2 Surface Reflectance imagery was filtered using the Lagos State study boundary and the May–October seasonal window for each year.

Cloud and shadow contamination was reduced using the Sentinel-2 Scene Classification Layer. The selected spectral bands were scaled to surface reflectance values.

### 5.2 Annual Composite Generation

A median composite was generated for each year from 2019 to 2025.

This produced seven annual seasonal composites, providing a consistent basis for temporal comparison.

### 5.3 Vegetation Index Computation

Two vegetation indices were calculated.

**Normalized Difference Vegetation Index (NDVI)**

NDVI measures the contrast between near-infrared and red reflectance.

NDVI = (NIR − Red) / (NIR + Red)

**Enhanced Vegetation Index (EVI)**

EVI incorporates blue-band information to improve vegetation sensitivity and reduce some atmospheric and canopy background influences.

EVI = 2.5 × (NIR − Red) / (NIR + 6Red − 7.5Blue + 1)

For EVI, pixels with unstable denominators and values outside the range of −1 to +1 were masked to reduce numerical artefacts.

### 5.4 LGA-Level Statistical Analysis

Mean NDVI and EVI values were calculated for each of the 20 LGAs for every year.

The resulting dataset contains 140 observations, representing 20 LGAs across seven years, with no missing NDVI or EVI values in the final statistical table.

### 5.5 Temporal and Spatial Comparison

The analysis included:

- State-wide annual NDVI and EVI trends.
- LGA-level annual vegetation index heatmaps.
- Endpoint comparison between 2019 and 2025.
- Spatial comparison of index changes across the 20 LGAs.

### 5.6 Animation

An annual NDVI animation was produced to communicate changes in vegetation greenness from 2019 to 2025.

The final presentation includes annual year labels, LGA boundaries, a consistent colour scale and a legend explaining low, moderate and high greenness.

## 6. Key Findings

### 6.1 State-Wide Temporal Patterns

The state-wide annual mean values showed variations in vegetation greenness during the study period.

| Year | Mean NDVI | Mean EVI |
|---|---:|---:|
| 2019 | 0.3687 | 0.3074 |
| 2020 | 0.3616 | 0.2930 |
| 2021 | 0.3674 | 0.3043 |
| 2022 | 0.3518 | 0.3117 |
| 2023 | 0.3835 | 0.3157 |
| 2024 | 0.3804 | 0.3020 |
| 2025 | 0.3609 | 0.3085 |

Both indices reached their highest annual state-wide mean in 2023 within the study period.

NDVI declined between 2023 and 2025, while EVI showed a slight recovery in 2025 following its 2024 decline.

### 6.2 LGA-Level Endpoint Comparison

The comparison of 2019 and 2025 mean index values revealed different patterns across the 20 LGAs.

**NDVI**
- 14 LGAs recorded a decline.
- 6 LGAs recorded an increase.
- The largest decline occurred in Lagos Island (−0.0795).
- The largest increase occurred in Ibeju Lekki (+0.0265).

**EVI**
- 16 LGAs recorded a decline.
- 4 LGAs recorded an increase.
- The largest decline occurred in Eti-Osa (−0.0277).
- The largest increase occurred in Epe (+0.0185).

Eti-Osa, Amuwo Odofin and Lagos Island recorded declines in both indices. Ibeju Lekki and Badagry recorded increases in both.

These results demonstrate spatial differences in vegetation greenness patterns across the state.

## 7. Visual Outputs

The project generates the following outputs:

- Annual NDVI maps (2019–2025).
- Annual EVI maps (2019–2025).
- State-wide temporal trend chart.
- LGA-level NDVI heatmap.
- LGA-level EVI heatmap.
- 2019–2025 NDVI endpoint comparison.
- Annual NDVI animation.

Selected maps, charts and the animation are presented on the accompanying portfolio website.

## 8. Tools and Technologies

- **Google Earth Engine:** Satellite imagery processing and cloud-based geospatial analysis.
- **Python:** Data processing and statistical analysis.
- **Google Colab:** Cloud-based computational environment.
- **GeoPandas / Pandas:** Tabular and geospatial data handling.
- **Matplotlib / Seaborn:** Data visualisation and heatmaps.
- **ImageIO / Pillow:** Animation and image processing.

## 9. Limitations and Interpretation

1. NDVI and EVI are spectral indicators of vegetation greenness, not direct measurements of vegetation health, biomass or ecological condition.
2. The May–October seasonal window provides a consistent period for annual comparison but does not represent the full annual vegetation cycle.
3. Cloud masking and the availability of clear satellite observations may affect the spatial coverage of individual annual composites.
4. LGA-level mean values can conceal local variations within individual administrative areas.
5. GAUL 2015 administrative boundaries were used as the reporting framework; boundary changes after that reference year were not independently assessed.
6. The observed index changes do not establish their underlying causes. Additional land-use, climate and field-based evidence would be required for causal interpretation.

## 10. Project Significance

This project demonstrates the application of cloud-based Earth observation, vegetation indices and geospatial data analytics to environmental monitoring at an urban and regional scale.

By combining satellite image processing with administrative-level statistical analysis, it provides a reproducible framework for examining spatial and temporal variations in vegetation greenness.

The workflow also demonstrates how remote sensing and data science can be integrated to generate accessible visual evidence for environmental assessment and decision support.

## 11. Repository Contents

The repository will contain:

- `README.md` — Project documentation.
- `notebooks/` — Google Colab notebooks and exported analysis code.
- `outputs/` — Selected maps, charts and statistical outputs.
- `animation/` — Final annual NDVI animation or a link to the hosted video.

## 12. Author

**Geospatial Data Science | Remote Sensing | Environmental Monitoring**

This project was independently developed using Google Earth Engine and Python.

For the visual presentation of the research, maps and animated outputs, visit the accompanying portfolio website.
