# Tracking the Streets: NYC Taxi Patterns Over Time

## Project Overview

This project presents a detailed analysis of the 2017 New York City Yellow Taxi dataset with a primary focus on two features: **fare per mile** and **trip volume over time**. Time series analysis techniques were used to examine trends, seasonality, and stationarity. The project evaluates various forecasting models, primarily SARIMA and SARIMAX, and discusses the limitations of traditional statistical models in capturing complex patterns.

## Dataset

- **Source**: New York City Taxi & Limousine Commission  
- **URL**: https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page?ref=hackernoon.com  
- **Year**: 2017 Yellow Taxi Trips  
- **Size**: ~13 GB (uncompressed CSVs)  
- **Fields Used**: `tpep_pickup_datetime`, `tpep_dropoff_datetime`, `trip_distance`, `fare_amount`

## Techniques and Methods

- Exploratory Data Analysis (EDA)
- Feature engineering: Fare per mile calculation
- Outlier removal and data cleaning
- Time series decomposition using STL
- Augmented Dickey-Fuller Test for stationarity
- ACF and PACF analysis
- SARIMA and SARIMAX modeling
- Residual diagnostics
- Model selection using AIC
- Evaluation metrics: RMSE, MAE, MAPE, R-squared

## Project Structure
├── data/ # Raw and cleaned data
├── notebooks/ # Jupyter notebooks for EDA and modeling
├── src/ # Python scripts
├── reports/ # Generated plots and report content
└── README.md # Project documentation


## Key Results

| Feature         | Best Model              | RMSE   | MAE    | MAPE   | R-squared |
|----------------|--------------------------|--------|--------|--------|-----------|
| Fare per Mile  | SARIMA(2,0,2)(0,1,1,24) | 0.4999 | 0.3890 | 6.38%  | 0.6523    |
| Trip Volume    | SARIMA(1,1,0)(1,1,0,24) | 854.2  |   –    | 31%    | 0.9586    |

## Insights

- Fare per mile is generally lower on weekends and higher during early morning hours.
- Volume of trips increases sharply during typical commute hours (7–9 AM and 4–7 PM).
- Fridays and Saturdays see higher fare rates and trip volumes late at night.
- A strong daily and weekly seasonality pattern exists in both fare and ride volume.
- SARIMA performs well for trip volume but fails to capture the complexity of fare patterns due to nonlinear dependencies.


