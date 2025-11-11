## 🎯Project Purpose  
To analyze and forecast CO air quality levels in Los Angeles using time-series modeling in R, with the goal of understanding long-term trends and predicting future pollutant behavior for environmental and public health planning.

## 📊 Data Source
https://www.epa.gov/outdoor-air-quality-data/air-quality-index-daily-values-report

- **Type:** Daily CO readings
- **Location:** Los Angeles CA
- **Time Range:** 2014.01.01–2024.10.01
- **Used Format:** Converted to *monthly averages* for time-series modeling.

## 📦 R Packages Used
The analysis and modeling were performed in **R**, using the following packages:

library(ggplot2)
library(tidyverse)
library(dplyr)
library(lubridate)
library(forecast)
library(tseries)
library(stats)
library(zoo)


## 🧠 Methodology Overview
1. Data Cleaning & Outlier Handling (IQR method)
2. Aggregation to Monthly Series
3. Train-Test Split (115 months train / 15 months test)
4. EDA
5. Stationarity Testing (ADF)
6. Model Comparison:
   - SARIMA
   - Exponential Smoothing 
7. Model Selection using AIC/BIC & Forecast Accuracy
8. Residual Diagnostics (Ljung–Box Test)


## ✅ Final Model Selected
**SARIMA (Seasonal ARIMA)** was selected due to:
- Lower **AIC** and **BIC**
- Lower **MAE**, **RMSE**, and **MAPE**
- No autocorrelation left in residuals

### Test Set Performance:
| Metric | Value |
|------|------|
| RMSE | ~1.26 |
| MAE  | ~0.91 |
| MAPE | ~12.7% |


## 🔮 6-Month Forecast
The model predicts continued *seasonal fluctuation* with a mild long-term decline in CO concentration.


## 🎯 Recommendations
- Use **multivariate forecasting** by adding temperature, wind speed, & traffic flow.
- Collect **hourly** instead of daily data for higher resolution.
- Extend dataset beyond 10 years for more robust forecasting.

## 📝 License
MIT License (Free to use & modify)

📊 Coursework Project — Time Series Air Quality Forecasting
-Institute: National Institute of Business Management (NIBM), Sri Lanka
-Programme: Higher National Diploma in Data Science (HNDDS)
-Student: K.D.Senaya Amarasinghe.


