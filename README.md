# Understanding Air Pollutants and AQI in India from 2015-2020 Using a VAR Model

Final research project for ECON 586 (Econometrics II) at California State University, Long Beach, Spring 2021.

The project studies how six pollutants (PM2.5, PM10, NO2, CO, SO2, O3) relate to the Air Quality Index across Indian cities between January 2015 and July 2020. Daily observations are aggregated to weekly series, tested for stationarity, and modeled with a vector autoregression. The analysis covers lag selection, Granger and instantaneous causality, a structural VAR, impulse responses, and forecast error variance decomposition.

The full write-up is in [MychelleHale_FinalProject.pdf](MychelleHale_FinalProject.pdf).

## Contents

| Path | Description |
|---|---|
| `MychelleHale_FinalProject.pdf` | Final paper |
| `India/CalcAQI.ipynb` | Python notebook that cleans the raw hourly data, computes AQI, and writes the daily CSVs |
| `India/MychelleHaleFinalProject.Rmd` | R Markdown with the time-series analysis |
| `India/df_day.csv` | Daily averages across all stations (main input to the R analysis) |
| `India/df_city_day.csv`, `India/df_station_day.csv` | Daily data by city and by station |

## Data

The raw data comes from India's Central Pollution Control Board and was obtained from the Kaggle dataset [Air Quality Data in India (2015 - 2020)](https://www.kaggle.com/rohanrao/air-quality-data-in-india). The raw files are not included in this repository. To rerun the notebook, download `station_hour.csv`, `station_day.csv`, `city_hour.csv`, `city_day.csv` and `stations.csv` from Kaggle into `India/`.

The R analysis runs from the processed CSVs included here, so the raw files are only needed to regenerate them.

## Running the analysis

The notebook needs Python 3 with `numpy` and `pandas`.

The R Markdown file needs these packages:

```r
install.packages(c("knitr", "sandwich", "fUnitRoots", "ggplot2", "forecast", "vars",
                   "urca", "TSstudio", "dplyr", "imputeTS", "tidyverse", "lubridate", "aweek"))
```

Knit `India/MychelleHaleFinalProject.Rmd` from the `India/` directory so the relative paths to the CSVs resolve.
