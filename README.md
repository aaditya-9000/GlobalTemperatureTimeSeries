# 🌍 Global Land Temperature Time Series Analysis & SARIMA Forecasting

An end-to-end econometric and statistical time series analysis of global surface land temperatures using historical monthly observations (from 1750 to 2015).

## 📌 Project Overview
This project explores centuries of global temperature records (starting from 1750 to 2015) to understand climate trends, isolate seasonal cycles, and build a robust forecasting model using **R**.

## 🛠️ Technical Stack & Libraries
* **Language:** R
* **Core Packages:** `forecast`, `tseries`, `tidyverse`, `lubridate`
* **Statistical Methods:** 
  * Time Series Conversion (`ts`)
  * Augmented Dickey-Fuller (ADF) Test for Stationarity
  * Autocorrelation (ACF) and Partial Autocorrelation (PACF) Diagnostics
  * Seasonal ARIMA (SARIMA) Modeling with Drift
  * Out-of-Sample Forecasting & Residual Diagnostics

## 📊 Methodology & Workflow

1. **Data Preprocessing:** Cleaned the Berkeley Earth global temperature dataset, filtered for `LandAverageTemperature`, and removed missing values.
2. **Time Series Initialization:** Converted data into a formal monthly R `ts` object starting from January 1750 (`frequency = 12`).
3. **Stationarity & Dependence Checks:** Verified stationarity characteristics using the ADF test and analyzed lag dependencies via ACF and PACF plots to identify seasonal patterns.
4. **Model Training:** Fitted an automated `SARIMA(2,0,2)(2,1,0)[12] with drift` model to capture both short-term monthly momentum and annual climate cycles.
5. **Diagnostics & Forecasting:** Evaluated residual white noise behavior (`ACF1 near 0.014`) and generated a 5-year out-of-sample forecast with confidence intervals.

## 🚀 Key Findings

* **Stationarity:** The series exhibited stability around its historical mean, while seasonal differencing (`D = 1`) effectively isolated the repeating 12-month annual cycle.
* **Model Performance:** The chosen SARIMA specification successfully extracted predictable temporal signals, leaving behind clean white noise errors.
* **Trend Analysis:** Included a positive drift parameter capturing the underlying secular warming trajectory over the centuries.
