Tandy Center Daily Data Reports
================

Tallies of various data products maintained at [Tandy Center got Ocean
Forecasting](https://www.bigelow.org/services/ocean-forecasting/) and
the [Computational Oceanography
Lab](https://www.bigelow.org/science/lab/computational-oceanography/)

- `firstdate` `lastdate` first an last recorded dates (there may be some
  missing between)
- `per` the period of time the variable represents
- `param` short hand parameter name
- `count` number of records available
- `age` the time between the current report date, `2025-05-22`, and the
  most recent record. Negative is a forecast date ahead of run date.

## [Copernicus NWA Ocean Physics Reanalysis](https://data.marine.copernicus.eu/product/GLOBAL_MULTIYEAR_PHY_001_030/description) for Northwest Atlantic GLOBAL_MULTIYEAR_PHY_001_030

| firstdate  | lastdate   | per | param   | count | age       |
|:-----------|:-----------|:----|:--------|------:|:----------|
| 1993-01-01 | 2021-06-30 | day | bottomT | 10408 | 1422 days |
| 1993-01-01 | 2021-06-30 | day | mlotst  | 10408 | 1422 days |
| 1993-01-01 | 2021-06-30 | day | so      | 10408 | 1422 days |
| 1993-01-01 | 2021-06-30 | day | thetao  | 10408 | 1422 days |
| 1993-01-01 | 2021-06-30 | day | uo      | 10408 | 1422 days |
| 1993-01-01 | 2021-06-30 | day | vo      | 10408 | 1422 days |
| 1993-01-01 | 2021-06-30 | day | zos     | 10408 | 1422 days |

## [Copernicus NWA Ocean Physics Analysis and Forecast](https://data.marine.copernicus.eu/product/GLOBAL_ANALYSISFORECAST_PHY_001_024/description) for Northwest Atlantic GLOBAL_ANALYSISFORECAST_PHY_001_024

| firstdate  | lastdate   | per | param  | count | age    |
|:-----------|:-----------|:----|:-------|------:|:-------|
| 2022-06-01 | 2025-05-20 | day | mlotst |  1062 | 2 days |
| 2022-06-01 | 2025-05-20 | day | pbo    |  1062 | 2 days |
| 2022-06-01 | 2025-05-20 | day | so     |  1063 | 2 days |
| 2022-06-01 | 2025-05-20 | day | sob    |  1062 | 2 days |
| 2022-06-01 | 2025-05-20 | day | thetao |  1062 | 2 days |
| 2022-06-01 | 2025-05-20 | day | tob    |  1062 | 2 days |
| 2022-06-01 | 2025-05-20 | day | uo     |  1063 | 2 days |
| 2022-06-01 | 2025-05-20 | day | vo     |  1063 | 2 days |
| 2022-06-01 | 2025-05-20 | day | wo     |  1062 | 2 days |
| 2022-06-01 | 2025-05-20 | day | zos    |  1062 | 2 days |

## [Global Ocean Biogeochemistry Hindcast](https://data.marine.copernicus.eu/product/GLOBAL_MULTIYEAR_BGC_001_029/description) for World GLOBAL_MULTIYEAR_BGC_001_029

| firstdate  | lastdate   | per | param | count | age     |
|:-----------|:-----------|:----|:------|------:|:--------|
| 1993-01-01 | 2025-02-28 | day | chl   | 12537 | 83 days |
| 1993-01-01 | 2025-02-28 | day | no3   | 12537 | 83 days |
| 1993-01-01 | 2025-02-28 | day | nppv  | 12537 | 83 days |
| 1993-01-01 | 2025-02-28 | day | o2    | 12537 | 83 days |
| 1993-01-01 | 2025-02-28 | day | po4   | 12537 | 83 days |
| 1993-01-01 | 2025-02-28 | day | si    | 12537 | 83 days |

## [Global Ocean Biogeochemistry Analysis and Forecast](https://data.marine.copernicus.eu/product/GLOBAL_ANALYSISFORECAST_BGC_001_028/description) for World GLOBAL_ANALYSISFORECAST_BGC_001_028

`path = copernicus::copernicus_path("world", "GLOBAL_ANALYSISFORECAST_BGC_001_028") db = andreas::read_database(path) |>   select(date, period, variable) |>   group_by(variable, period) |>    group_map(     function(tbl, key){       count = nrow(tbl)       firstdate = min(tbl$date)       lastdate = max(tbl$date)       age = Sys.Date() - lastdate       dplyr::tibble(firstdate, lastdate,                      per = tbl$period[1],                     param = tbl$variable[1],                     count = count,                     age = age)     }, .keep = TRUE) |>   bind_rows() knitr::kable(db)`

## [OBPG](https://oceancolor.gsfc.nasa.gov/) for world (mixed resolutions, AQUA MODIS)

| firstdate  | lastdate   | per  | param   | res | count | age      |
|:-----------|:-----------|:-----|:--------|:----|------:|:---------|
| 2002-07-04 | 2023-11-30 | CU   | chlor_a | 9km |    47 | 539 days |
| 2003-06-01 | 2024-06-30 | MC   | chlor_a | 9km |    81 | 326 days |
| 2024-12-01 | 2024-12-31 | MO   | chlor_a | 4km |   285 | 142 days |
| 2002-09-21 | 2023-12-20 | SCAU | chlor_a | 9km |     7 | 519 days |
| 2003-03-21 | 2024-06-20 | SCSP | chlor_a | 9km |    11 | 336 days |
| 2002-06-21 | 2024-09-20 | SCSU | chlor_a | 9km |     8 | 244 days |
| 2002-12-21 | 2024-03-20 | SCWI | chlor_a | 9km |     8 | 428 days |
| 2023-01-01 | 2023-12-31 | YR   | chlor_a | 9km |    41 | 508 days |
| 2002-07-04 | 2023-11-30 | CU   | par     | 9km |    46 | 539 days |
| 2003-06-01 | 2024-06-30 | MC   | par     | 9km |    35 | 326 days |
| 2024-12-01 | 2024-12-31 | MO   | par     | 4km |   285 | 142 days |
| 2002-09-21 | 2023-12-20 | SCAU | par     | 9km |     7 | 519 days |
| 2003-03-21 | 2024-06-20 | SCSP | par     | 9km |    11 | 336 days |
| 2002-06-21 | 2024-09-20 | SCSU | par     | 9km |     8 | 244 days |
| 2002-12-21 | 2024-03-20 | SCWI | par     | 9km |     7 | 428 days |
| 2023-01-01 | 2023-12-31 | YR   | par     | 9km |    41 | 508 days |
| 2002-07-04 | 2023-11-30 | CU   | pic     | 9km |    45 | 539 days |
| 2003-06-01 | 2024-06-30 | MC   | pic     | 9km |    35 | 326 days |
| 2024-12-01 | 2024-12-31 | MO   | pic     | 4km |   285 | 142 days |
| 2002-09-21 | 2023-12-20 | SCAU | pic     | 9km |     7 | 519 days |
| 2003-03-21 | 2024-06-20 | SCSP | pic     | 9km |    11 | 336 days |
| 2002-06-21 | 2024-09-20 | SCSU | pic     | 9km |     8 | 244 days |
| 2002-12-21 | 2024-03-20 | SCWI | pic     | 9km |     7 | 428 days |
| 2023-01-01 | 2023-12-31 | YR   | pic     | 9km |    41 | 508 days |
| 2002-07-04 | 2023-11-30 | CU   | poc     | 9km |    45 | 539 days |
| 2003-06-01 | 2024-06-30 | MC   | poc     | 9km |    35 | 326 days |
| 2024-12-01 | 2024-12-31 | MO   | poc     | 4km |   285 | 142 days |
| 2002-09-21 | 2023-12-20 | SCAU | poc     | 9km |     7 | 519 days |
| 2003-03-21 | 2024-06-20 | SCSP | poc     | 9km |    11 | 336 days |
| 2002-06-21 | 2024-09-20 | SCSU | poc     | 9km |     8 | 244 days |
| 2002-12-21 | 2024-03-20 | SCWI | poc     | 9km |     7 | 428 days |
| 2023-01-01 | 2023-12-31 | YR   | poc     | 9km |    41 | 508 days |
| 2002-07-04 | 2024-11-30 | CU   | sst     | 9km |    21 | 173 days |
| 2003-06-01 | 2024-06-30 | MC   | sst     | 9km |    41 | 326 days |
| 2024-12-01 | 2024-12-31 | MO   | sst     | 4km |   275 | 142 days |
| 2002-09-21 | 2023-12-20 | SCAU | sst     | 9km |     6 | 519 days |
| 2003-03-21 | 2024-06-20 | SCSP | sst     | 9km |     6 | 336 days |
| 2002-06-21 | 2024-09-20 | SCSU | sst     | 9km |     6 | 244 days |
| 2002-12-21 | 2024-03-20 | SCWI | sst     | 9km |     6 | 428 days |
| 2023-01-01 | 2023-12-31 | YR   | sst     | 9km |    43 | 508 days |

## [OBPG](https://oceancolor.gsfc.nasa.gov/) for Northwest Atlantic (all 4km res, AQUA and TERRA MODIS)

| firstdate  | lastdate   | per  | param        | count | age      |
|:-----------|:-----------|:-----|:-------------|------:|:---------|
| 2004-01-16 | 2025-02-06 | 16DR | chlor_a      |  7693 | 105 days |
| 2004-02-01 | 2025-02-06 | 32DR | chlor_a      |  7677 | 105 days |
| 2004-01-08 | 2025-02-06 | 8DR  | chlor_a      |  7701 | 105 days |
| 2004-01-01 | 2025-02-06 | DAY  | chlor_a      |  7708 | 105 days |
| 2002-07-01 | 2023-12-01 | MO   | chlor_a      |   258 | 538 days |
| 2004-02-08 | 2022-11-30 | 8DR  | chlor_a_cum  |  6871 | 904 days |
| 2004-02-01 | 2022-11-30 | DAY  | chlor_a_cum  |  6878 | 904 days |
| 2004-02-08 | 2023-03-13 | 8DR  | chlor_a_fill |  6974 | 801 days |
| 2004-02-01 | 2023-03-13 | DAY  | chlor_a_fill |  6981 | 801 days |
| 2004-01-08 | 2025-02-06 | 8DR  | par          |  7701 | 105 days |
| 2004-01-01 | 2025-02-06 | DAY  | par          |  7708 | 105 days |
| 2002-07-01 | 2023-12-01 | MO   | par          |   258 | 538 days |
| 2004-01-08 | 2025-02-06 | 8DR  | pic          |  7701 | 105 days |
| 2004-01-01 | 2025-02-06 | DAY  | pic          |  7708 | 105 days |
| 2002-07-01 | 2023-12-01 | MO   | pic          |   258 | 538 days |
| 2004-01-08 | 2025-02-06 | 8DR  | poc          |  7701 | 105 days |
| 2004-01-01 | 2025-02-06 | DAY  | poc          |  7708 | 105 days |
| 2002-07-01 | 2023-12-01 | MO   | poc          |   258 | 538 days |
| 2004-01-08 | 2025-02-06 | 8DR  | sst          |  7700 | 105 days |
| 2004-01-01 | 2025-02-06 | DAY  | sst          |  7707 | 105 days |
| 2002-07-01 | 2023-11-01 | MO   | sst          |   256 | 568 days |
| 2004-01-08 | 2025-02-06 | 8DR  | sst_slope    |  7700 | 105 days |

## [MUR](https://podaac.jpl.nasa.gov/MEaSUREs-MUR) for Northwest Atlantic (all 0.01 degree res, daily)

| firstdate  | lastdate   | per | param     | count | age      |
|:-----------|:-----------|:----|:----------|------:|:---------|
| 2004-01-01 | 2025-05-20 | DAY | sst       |  7811 | 2 days   |
| 2004-01-01 | 2024-05-01 | MON | sst       |   245 | 386 days |
| 2004-01-01 | 2023-12-30 | DAY | sst_cum   |  7304 | 509 days |
| 2004-01-01 | 2025-05-20 | DAY | sst_slope |  7811 | 2 days   |

## [NAM](https://www.ncei.noaa.gov/products/weather-climate-models/north-american-mesoscale) for Northeast US and Eastern Canada (all 12km res, daily)

Negative age means days ahead of the current date.

| firstdate  | lastdate   | param   | trt   | count | age     |
|:-----------|:-----------|:--------|:------|------:|:--------|
| 2022-09-30 | 2025-05-25 | airtemp | max   |  7601 | -3 days |
| 2022-09-30 | 2025-05-25 | airtemp | mean  |  7601 | -3 days |
| 2022-09-30 | 2025-05-25 | airtemp | min   |  7601 | -3 days |
| 2022-09-30 | 2025-05-25 | cloud   | mean  |  2927 | -3 days |
| 2022-09-30 | 2025-05-25 | precip  | sum   |  7600 | -3 days |
| 2022-09-30 | 2025-05-25 | relhum  | mean  |  7601 | -3 days |
| 2022-09-30 | 2025-05-25 | sncvr   | mean  |  7595 | -3 days |
| 2022-09-30 | 2025-05-25 | sndep   | mean  |  7601 | -3 days |
| 2022-09-30 | 2025-05-25 | trnstr  | mean  |  7596 | -3 days |
| 2022-09-30 | 2025-05-25 | uwind   | mean  |  7601 | -3 days |
| 2022-09-30 | 2025-05-25 | vegcvr  | mean  |  7596 | -3 days |
| 2022-09-30 | 2025-05-25 | vegtyp  | first |  7596 | -3 days |
| 2022-09-30 | 2025-05-25 | vis     | mean  |  4441 | -3 days |
| 2022-09-30 | 2025-05-25 | vwind   | mean  |  7601 | -3 days |
| 2022-09-30 | 2025-05-25 | wilt    | mean  |  7596 | -3 days |

## [OISST](https://www.ncei.noaa.gov/products/optimum-interpolation-sst) for the world (0.25 degree res, daily and annual res)

| firstdate  | lastdate   | per | trt   | count | age      |
|:-----------|:-----------|:----|:------|------:|:---------|
| 1982-01-01 | 2024-01-01 | ann | max   |    43 | 507 days |
| 1982-01-01 | 2024-01-01 | ann | mean  |    43 | 507 days |
| 1982-01-01 | 2024-01-01 | ann | min   |    43 | 507 days |
| 1982-01-01 | 2024-01-01 | ann | range |    43 | 507 days |
| 1982-01-01 | 2024-01-01 | ann | sum   |    43 | 507 days |
| 1981-09-01 | 2025-05-20 | day | mean  | 15968 | 2 days   |

## [ERSST](https://www.ncei.noaa.gov/products/extended-reconstructed-sst) for the world (2 degree res, monthly res)

We retain both the anomaly and the computed values.

| firstdate  | lastdate   | anomaly | count | age     |
|:-----------|:-----------|:--------|------:|:--------|
| 1854-01-01 | 2025-03-01 | FALSE   |  2055 | 82 days |
| 1854-01-01 | 2025-03-01 | TRUE    |  2055 | 82 days |
