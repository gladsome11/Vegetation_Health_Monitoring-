# Methodology

## Lagos State Vegetation Greenness Monitoring (2019–2025)

### 1. Study Area

The study covers Lagos State, southwestern Nigeria. The analysis was conducted at two spatial levels:

- **State level:** to examine annual patterns in vegetation greenness across Lagos State.
- **Local Government Area (LGA) level:** to examine the spatial distribution and temporal variation of vegetation greenness across the state's 20 LGAs.

Administrative boundaries were obtained from the FAO Global Administrative Unit Layers (GAUL) 2015, Level 2 dataset. The dataset was filtered to identify Nigeria, Lagos State and its constituent LGAs.

The LGAs served as administrative reporting units. They should not be interpreted as independent ecological zones.

### 2. Data Source and Temporal Coverage

Sentinel-2 Level-2A Surface Reflectance Harmonized imagery was obtained from the Google Earth Engine catalogue:

`COPERNICUS/S2_SR_HARMONIZED`

The analysis covered seven years, from 2019 to 2025.

The selected seasonal observation window was 1 May to 1 November, representing May–October observations for each year.

The principal spectral bands used were:

| Band | Wavelength region | Spatial resolution | Application |
|---|---|---:|---|
| B2 | Blue | 10 m | EVI calculation |
| B4 | Red | 10 m | NDVI and EVI calculation |
| B8 | Near-infrared | 10 m | NDVI and EVI calculation |

The 2018 observation period was excluded because only one scene was available within the selected May–October seasonal window. Including it would have introduced a substantial difference in temporal observation coverage compared with the other years.

### 3. Image Preprocessing

Satellite imagery was filtered using the study area boundary, acquisition dates and cloud metadata.

Images with a `CLOUDY_PIXEL_PERCENTAGE` greater than or equal to 90% were excluded.

Additional cloud and scene-condition masking was performed using the Sentinel-2 Scene Classification Layer (SCL).

The following SCL classes were excluded:

- Class 1: Saturated or defective pixels
- Class 2: Dark area pixels
- Class 3: Cloud shadows
- Class 7: Unclassified pixels
- Class 8: Medium-probability clouds
- Class 9: High-probability clouds
- Class 10: Cirrus clouds
- Class 11: Snow or ice

The selected surface reflectance bands were converted using the Sentinel-2 scale factor of 0.0001 before vegetation index calculations.

### 4. Vegetation Index Calculation

Two spectral indices were calculated: Normalized Difference Vegetation Index (NDVI) and Enhanced Vegetation Index (EVI).

#### 4.1 Normalized Difference Vegetation Index (NDVI)

NDVI was calculated using the near-infrared and red spectral bands:

\[
NDVI = \frac{NIR-Red}{NIR+Red}
\]

For Sentinel-2:

\[
NDVI = \frac{B8-B4}{B8+B4}
\]

NDVI provides an indication of vegetation greenness based on the contrast between near-infrared and red reflectance.

#### 4.2 Enhanced Vegetation Index (EVI)

EVI was calculated using the near-infrared, red and blue bands:

\[
EVI = 2.5 \times
\frac{NIR-Red}
{NIR+6Red-7.5Blue+1}
\]

For Sentinel-2:

\[
EVI = 2.5 \times
\frac{B8-B4}
{B8+6B4-7.5B2+1}
\]

EVI was included to provide a complementary vegetation greenness indicator with additional sensitivity adjustments involving the blue band.

To reduce numerical instability, pixels with an absolute denominator value less than or equal to 0.1 were masked. EVI values outside the range of -1 to +1 were also excluded.

Both indices were retained as separate analytical variables.

### 5. Annual Composite Generation

For each year between 2019 and 2025, the filtered and preprocessed Sentinel-2 imagery was combined into an annual median composite.

The median reducer was applied independently to the NDVI and EVI image collections.

The resulting annual composites represent the median observed vegetation index values during the selected May–October period.

Seven annual composites were generated, each containing NDVI and EVI bands.

### 6. Spatial Statistical Analysis

#### 6.1 LGA-Level Analysis

The annual NDVI and EVI composites were summarised within the 20 Lagos State LGAs.

Mean vegetation index values were extracted for each LGA and year.

The resulting dataset contained:

- 20 LGAs
- 7 observation years
- 140 LGA-year records
- NDVI and EVI mean values

The final LGA-level dataset was checked for missing values and valid index ranges.

#### 6.2 State-Level Analysis

State-wide annual mean NDVI and EVI values were calculated using the mean reducer over the Lagos State study boundary.

This produced seven annual observations for each vegetation index.

The state-level statistics were calculated directly from the corrected annual image composites to maintain consistency with the final index calculation workflow.

### 7. Temporal and Spatial Comparison

Temporal variation was examined using annual state-level NDVI and EVI statistics.

LGA-level temporal patterns were visualised using heatmaps, allowing comparison of annual mean index values across administrative areas.

Endpoint change was calculated as:

\[
\Delta VI = VI_{2025} - VI_{2019}
\]

where \(VI\) represents either NDVI or EVI.

Negative values indicate a decrease in the mean index value between the two observation years, while positive values indicate an increase.

Endpoint differences were interpreted as changes in vegetation greenness indicators, rather than definitive measurements of vegetation loss or gain.

### 8. Visualisation and Output Generation

The following outputs were produced:

- Annual NDVI animation covering 2019–2025.
- LGA-level NDVI heatmap.
- LGA-level EVI heatmap.
- State-wide annual NDVI and EVI trend chart.
- LGA-level vegetation statistics in CSV format.
- State-wide annual vegetation statistics in CSV format.

The visual outputs were designed to communicate both temporal patterns and spatial differences across the study area.

### 9. Tools and Processing Environment

The analysis used the following tools and technologies:

| Tool | Application |
|---|---|
| Google Earth Engine | Satellite image retrieval and cloud-based geospatial processing |
| Google Colab | Python-based analysis and visualisation |
| Earth Engine Python API | Satellite image processing and statistical extraction |
| Pandas and NumPy | Data manipulation and validation |
| Matplotlib and Seaborn | Charts and heatmaps |
| Pillow (PIL) | Presentation-frame preparation and animation |
| GitHub | Source code, documentation and output storage |

### 10. Limitations

The following limitations should be considered when interpreting the results:

1. **Seasonal coverage:** The analysis represents May–October observations and does not describe vegetation conditions throughout the entire calendar year.

2. **Cloud contamination:** Although cloud and scene-condition masking was applied, residual atmospheric and classification errors may remain.

3. **Spatial aggregation:** LGA-level mean values can conceal local variations within individual administrative areas.

4. **Indicator limitations:** NDVI and EVI represent spectral vegetation greenness responses. They do not directly measure vegetation health, biomass, species composition or ecological condition.

5. **Temporal interpretation:** Differences between 2019 and 2025 do not independently establish the causes of observed index changes.

6. **Administrative boundaries:** GAUL 2015 boundaries were used as reporting units and may not reflect subsequent administrative boundary changes.

7. **Observation consistency:** Differences in image availability and observation conditions may influence annual composite values.

### 11. Reproducibility

The Google Earth Engine processing workflow, analysis notebook, statistical datasets and visual outputs are organised within this GitHub repository.

The notebook provides the computational workflow used to generate the annual vegetation composites, extract spatial statistics and produce the visual outputs.

**Study period:** 2019–2025  
**Study area:** Lagos State, Nigeria  
**Spatial reporting units:** 20 LGAs  
**Primary indicators:** NDVI and EVI  
**Satellite data:** Sentinel-2 Surface Reflectance Harmonized
