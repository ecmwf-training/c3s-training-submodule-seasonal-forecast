![logo](https://climate.copernicus.eu/sites/default/files/custom-uploads/branding/LogoLine_horizon_C3S.png)

# C3S seasonal forecasts training notebooks

Seasonal forecasts sit between weather and climate predictions, providing short-term climate outlooks focused on average conditions and variability. They help us to forecast what kind of season to expect, but not what will happen on a given day, providing forecasts over longer time horizons typically spanning several weeks to months. In this way, they help people and sectors prepare for climate-related risks and opportunities months in advance, helping society make smarter, climate-informed decisions. Seasonal forecasts are probabilistic predictions, not certainties. As such, it is important to interpret them as guidance, not guarantees, and use them alongside other sources of information for planning and decision-making.

With this in mind, this tutorial series explores the use and interpretation of seasonal forecast data available through C3S for various applications, including agriculture, water resource management, and disaster preparedness. They equip you with the skills to access, explore, and use the seasonal forecast data, getting information from it in a form you can use alongside the other sources of information needed for optimised planning and decision-making.

The tutorials in this series are:

## 1. Seasonal forecast anomalies

This notebook tutorial provides a practical introduction to calculating seasonal forecast anomalies with data from the Copernicus Climate Change Service (C3S). C3S seasonal forecast products are based on data from several state-of-the-art seasonal prediction systems. In this tutorial we shall focus on the [ECMWF SEAS5 model](https://confluence.ecmwf.int/display/CKB/Description+of+SEAS5+C3S+contribution), which is one of the forecasting systems available through C3S.

The tutorial demonstrates how to access real-time forecast data of total precipitation, and hindcast data. You will then extract data on a sub-region of South Asia, before computing a climate mean for the reference period, and calculating 3-month anomalies. Over the course of the data analysis, you will also be visualising your calculation your calculations as both spatial maps, time-series and interactive plots, equipping yourself to reproduce [charts similar to those available through C3S](https://climate.copernicus.eu/charts/c3s_seasonal/).

![logo](./img/.png)

## 2. Seasonal forecast verification

This notebook provides a practical introduction on how to produce some verification metrics and scores for seasonal forecasts with data from the Copernicus Climate Change Service (C3S). C3S seasonal forecast products are based on data from several state-of-the-art seasonal prediction systems. In this notebook, as an example, you will focus on data produced by one of these systems ([CMCC SPSv3.5 system](https://confluence.ecmwf.int/display/CKB/Description+of+CMCC-CM2-v20191201+C3S+contribution)), whose data are available through the C3S.

The tutorial demonstrates how to access retrospective forecast (hindcast) data, and complementary reanalysis data (ERA5, which combines observations with model outputs) from the CDS. You will then compute some deterministic products (anomalies) and some probabilistic products (probabilities for tercile categories). In addition to the 1-month average data retrieved from the CDS, 3-months aggregations will be also produced, before you calculate verification metrics (correlation, area under the ROC curve, and RPS), and visualise your findings in a set of plots.

![logo](./img/.png)
