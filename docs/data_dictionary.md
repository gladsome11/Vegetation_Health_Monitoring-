# Data Dictionary

## Lagos State Vegetation Greenness Monitoring (2019–2025)

This document describes the structure, variables and interpretation of the datasets generated for the Lagos State Vegetation Greenness Monitoring project.

Two CSV datasets are provided:

1. LGA-level vegetation statistics.
2. State-level annual vegetation statistics.

Both datasets contain mean NDVI and EVI values derived from Sentinel-2 Surface Reflectance imagery.

## 1. LGA-Level Vegetation Statistics

**Filename:** `Lagos_LGA_Vegetation_Statistics_2019_2025.csv`

**Dataset dimensions:** 140 records × 4 columns.

Each record represents the mean vegetation index values for one Local Government Area (LGA) in one observation year.

| Column | Data type | Description |
|---|---|---|
| `ADM2_NAME` | String | Name of the Local Government Area |
| `year` | Integer | Observation year (2019–2025) |
| `NDVI` | Float | Mean Normalized Difference Vegetation Index for the LGA |
| `EVI` | Float | Mean Enhanced Vegetation Index for the LGA |

### Dataset structure

- 20 LGAs
- 7 observation years
- 140 LGA-year records
- 2 vegetation indices
- No missing values in the final dataset

### Interpretation

NDVI and EVI values are dimensionless and generally range from -1 to +1.

Higher positive values commonly indicate stronger vegetation greenness responses, while lower values may indicate reduced vegetation greenness or a greater presence of non-vegetated surfaces.

Values should be interpreted within the context of the seasonal observation period and the limitations of satellite-derived vegetation indices.

## 2. State-Level Annual Vegetation Statistics

**Filename:** `Lagos_State_Vegetation_Trends_2019_2025.csv`

**Dataset dimensions:** 7 records × 3 columns.

Each record represents the annual mean vegetation index values calculated across the Lagos State study boundary.

| Column | Data type | Description |
|---|---|---|
| `year` | Integer | Observation year (2019–2025) |
| `NDVI` | Float | State-wide mean Normalized Difference Vegetation Index |
| `EVI` | Float | State-wide mean Enhanced Vegetation Index |

### Dataset structure

- 7 annual records
- 2 vegetation indices
- No missing values in the final dataset

### Interpretation

The state-level dataset provides an overview of annual vegetation greenness patterns across Lagos State.

It is useful for examining broad temporal variation but does not reveal the distribution of changes among individual LGAs.

## 3. Variable Definitions

### Normalized Difference Vegetation Index (NDVI)

NDVI measures the contrast between near-infrared and red reflectance.

\[
NDVI = \frac{B8-B4}{B8+B4}
\]

Where:

- B8 represents Sentinel-2 near-infrared reflectance.
- B4 represents Sentinel-2 red reflectance.

NDVI is used as an indicator of vegetation greenness.

### Enhanced Vegetation Index (EVI)

EVI incorporates near-infrared, red and blue reflectance.

\[
EVI = 2.5 \times
\frac{B8-B4}{B8+6B4-7.5B2+1}
\]

Where:

- B8 represents near-infrared reflectance.
- B4 represents red reflectance.
- B2 represents blue reflectance.

EVI provides a complementary vegetation greenness indicator.

## 4. Temporal Coverage

Both datasets cover the period 2019–2025.

Annual values were derived from median satellite image composites generated using observations acquired between 1 May and 1 November of each year.

The datasets therefore represent seasonal vegetation greenness patterns rather than full-calendar-year conditions.

## 5. Endpoint Change Interpretation

The project also examines differences between the first and last observation years.

\[
\Delta VI = VI_{2025} - VI_{2019}
\]

Interpretation:

- **Negative change:** The mean vegetation index decreased between 2019 and 2025.
- **Positive change:** The mean vegetation index increased between 2019 and 2025.
- **Near-zero change:** The mean index showed relatively little difference between the two endpoints.

These differences describe changes in spectral vegetation indices. They should not automatically be interpreted as confirmed vegetation loss or gain.

## 6. Data Quality and Validation

The final datasets were checked for:

- Expected observation years.
- Expected number of LGA records.
- Missing values.
- Valid NDVI and EVI ranges.
- Consistency between the annual observation period and dataset labels.

The final LGA dataset contains 140 records, while the state-level dataset contains seven annual records.

## 7. Important Analytical Considerations

1. **Spatial aggregation:** LGA-level means summarise observations within administrative boundaries and may conceal local differences.

2. **State-level aggregation:** State-wide mean values are calculated across valid pixels within the state boundary. They are not necessarily equal to the simple arithmetic average of the 20 LGA means.

3. **Index interpretation:** NDVI and EVI measure spectral vegetation responses, not direct vegetation health, biomass or species diversity.

4. **Seasonal representation:** Annual values represent the selected May–October observation window.

5. **Causal interpretation:** The datasets alone cannot establish the environmental or human causes of observed changes.

## 8. File Organisation

The datasets are stored in the repository under:

```text
outputs/
└── data/
    ├── Lagos_LGA_Vegetation_Statistics_2019_2025.csv
    └── Lagos_State_Vegetation_Trends_2019_2025.csv
```

The datasets are intended to support further statistical analysis, visualisation and geospatial investigation of vegetation greenness patterns across Lagos State.

**Study period:** 2019–2025  
**Study area:** Lagos State, Nigeria  
**Reporting units:** 20 LGAs  
**Primary indicators:** NDVI and EVI
