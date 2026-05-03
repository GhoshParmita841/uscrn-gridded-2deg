# USCRN Gridded Daily Climate Data (2006–2021)

## Overview
Daily 2°-resolution gridded products for 5 hydroclimatic variables across CONUS,
Alaska, and Hawaii, generated from USCRN station observations using a
two-stage geostatistical pipeline.

## Methodology
1. **AIC screening** — 5 candidate variogram models (spherical, exponential,
   gaussian, linear, circular) ranked per variable per region
2. **Stable model pair selection** — AIC top-1 + spherical anchor (replaces
   numerically-unstable circular for n=207 CONUS stations)
3. **Daily kriging / IDW** — both candidates evaluated across all 5,844 days
4. **ERA5 RMSE validation** — independent winner selection per (region × variable)
5. **Spatial-variance check** — confirms outputs are genuine spatial fields

## Variables
| Variable | Units | Description |
|----------|-------|-------------|
| AirTemperature | °C | Near-surface air temperature |
| Precipitation | mm | Daily total precipitation |
| RelativeHumidity | % | Near-surface relative humidity |
| SoilTemperature | °C | Soil temperature (5 cm) |
| SoilMoisture | m³/m³ | Soil moisture (10 cm) |

## Files
- **13 NetCDF files** (CF-1.8 compliant, the winning gridded products)
- **MANIFEST.json** — full file inventory + AIC justification + MD5 checksums
- **evidence/** — supporting CSVs documenting model selection and statistical analysis

## License
CC-BY 4.0 — free reuse with attribution.
