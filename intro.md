![logo](https://climate.copernicus.eu/sites/default/files/custom-uploads/branding/LogoLine_horizon_EC_Cop_ECMWF.png)

# C3S Seasonal Forecasts Training notebooks

**PLEASE NOTE THAT THIS A DEVELOPMENT INSTANCE, THESE NOTE BOOKS ARE OFFICIALLY PUBLISHED ELSEWHERE**

This Jupyter book is a sub-module of the core C3S training material, it is published here for reviewing the
content prior to publication.

Seasonal forecasts provide valuable insights into expected climate conditions over longer time horizons, typically spanning several weeks to months. This tutorial series explores the interpretation and utilization of seasonal forecast data for various applications, including agriculture, water resource management, and disaster preparedness.

## [Seasonal Forecast Anomalies](../notebooks/sf-anomalies/sf-anomalies.ipynb)

This notebook provides a practical introduction to calculating seasonal forecast anomalies with data from the Copernicus Climate Change Service (C3S). C3S seasonal forecast products are based on data from several state-of-the-art seasonal prediction systems. In this tutorial we shall focus on the [ECMWF SEAS5 model](https://confluence.ecmwf.int/display/CKB/Description+of+SEAS5+C3S+contribution), which is one of the forecasting systems available through C3S.

The tutorial will demonstrate how to access real-time forecast data of total precipitation, with a forecast start date in May 2021 and 6 monthly lead times (up to October 2021). Hindcast data for the same start date and lead-time months in the reference period 1993 to 2016 will also be downloaded. The tutorial will then show how to extract a subset area over South Asia for both the forecast and hindcast data. The climate mean for the reference period will be computed and this reference mean will be subtracted from the real-time forecast data to derive monthly anomalies. These will be visualised as both spatial maps and time series. Finally, 3-monthly anomalies will be calculated and visualised in an interactive plot, as a demonstration of how to reproduce similar [charts available through C3S](https://climate.copernicus.eu/charts/c3s_seasonal/).

![logo](./img/.png)

## [Seasonal Forecast Verification](../notebooks/sf-verification/sf-verification.ipynb)

This notebook provides a practical introduction on how to produce some verification metrics and scores for seasonal forecasts with data from the Copernicus Climate Change Service (C3S). C3S seasonal forecast products are based on data from several state-of-the-art seasonal prediction systems. In this notebook, as an example, we will focus on data produced by [CMCC SPSv3.5 system](https://confluence.ecmwf.int/display/CKB/Description+of+CMCC-CM2-v20191201+C3S+contribution), which is one of the forecasting systems available through C3S.

The tutorial will demonstrate how to access retrospective forecast (hindcast) data of 2-metre temperature initialized in the period 1993-2016, with a forecast start date in the 1st of March. All these forecasts are 6 months long (from March to August). More details about the role of the hindcasts can be found in [this Copernicus Knowledge Base article](https://confluence.ecmwf.int/display/CKB/Seasonal+forecasts+and+the+Copernicus+Climate+Change+Service). Observation data (ERA5 reanalysis) for the same reference period, 1993 to 2016, and the same months will also be obtained from the CDS. The tutorial will then show how to compute some deterministic products (anomalies) and some probabilistic products (probabilities for tercile categories). In addition to the 1-month average data retrieved from the CDS, 3-months aggregations will be also produced. Finally, verification metrics (correlation, area under the ROC curve, and RPS) will be calculated and visualised in a set of plots.

![logo](./img/.png)