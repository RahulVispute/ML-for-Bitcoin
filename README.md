# Bitcoin Price Analysis

## Overview
This project explores the application of machine learning and statistical methods to predict Bitcoin's closing prices. Using historical data from April 19, 2019, to April 19, 2024, the project applies various analytical techniques, including ARIMA, Gradient Boosting Regressor, and Random Forest Regressor, to provide short-term and long-term price forecasts. The goal is to understand market trends, volatility, and predictive accuracy to assist investors and policymakers.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Motivation](#motivation)
3. [Dataset](#dataset)
4. [Preprocessing](#preprocessing)
5. [Data Exploration](#data-exploration)
6. [Models and Techniques](#models-and-techniques)
7. [Results](#results)
8. [Discussion](#discussion)
9. [Summary](#summary)
10. [References](#references)

---

## Introduction
Bitcoin, introduced in 2009 by the pseudonymous Satoshi Nakamoto, represents a transformative development in digital currency and blockchain technology. This project aims to analyze the price trends, technical underpinnings, and predictive factors influencing Bitcoin's market behavior.

---

## Motivation
The analysis is driven by the complexities of Bitcoin's technology, its economic implications, and its impact on financial inclusivity, privacy, and global markets. By understanding its historical trends and market behavior, this study provides insights into Bitcoin's future trajectory.

---

## Dataset
The dataset includes 1828 daily entries with the following features:
- **Date**: The trading day.
- **Open, High, Low, Close, Adj Close**: Bitcoin price metrics.
- **Volume**: Daily trade volume.

Source: Yahoo Finance (BTC-USD).

---

## Preprocessing
The preprocessing phase ensures the data is clean, formatted, and suitable for model training and evaluation. Various techniques were applied to handle missing data, transform features, and prepare the dataset for analysis.

### 1. ARIMA Model Preprocessing
- **Feature Selection**:
  - Selected the daily **closing prices** as the primary feature due to their stability and ability to represent market sentiment at the end of the trading day.
- **Stationarity Transformation**:
  - Applied **log transformation** to stabilize variance and mean over time.
  - Used **differencing** (subtracting consecutive observations) to remove non-stationary trends.
  - Conducted **Dickey-Fuller tests** to verify stationarity after preprocessing. Results confirmed stationarity after transformations.
- **Trend Smoothing**:
  - Calculated **7-day moving averages** to smooth short-term fluctuations and highlight longer-term trends.
  - Applied **Exponential Weighted Moving Averages (EWMA)** with a 7-day half-life to emphasize recent data points.
- **Data Segmentation**:
  - Split the data into **training (80%)** and **testing (20%)** sets for model training and validation.

### 2. Random Forest and Gradient Boosting Regressors Preprocessing
- **Handling Missing Data**:
  - Imputed missing values using **forward filling** to ensure continuity without introducing biases.
- **Feature Engineering**:
  - Retained the 'Date' column for chronological structuring but excluded it as a direct input to regression models.
  - Engineered moving averages and volatility indices as additional predictors to capture market trends and fluctuations.
- **Normalization**:
  - Scaled features like **volume** to reduce the impact of outliers.
- **Data Segmentation**:
  - Similar to ARIMA preprocessing, the dataset was split into **training (80%)** and **testing (20%)** sets, preserving chronological order to reflect the time series nature.

---

## Data Exploration
The dataset was extensively analyzed to uncover patterns, trends, and anomalies, providing insights that guided preprocessing and model selection.

### 1. Price Trend Visualization
- **Line Plot**:
  - Visualized Bitcoin's daily **closing prices** over time (2019–2024) using a line plot.
  - Key Observations:
    - High volatility with sharp rises and falls.
    - Evidence of periodic cycles and abrupt price changes, typical of cryptocurrency markets.

### 2. Log Transformation
- Applied **log transformation** to the 'Close' price:
  - Stabilized variance and mitigated the impact of extreme values.
  - Improved stationarity and model performance.

### 3. Rolling Statistics
- **7-day Rolling Mean**:
  - Smoothed time series data to highlight trends and minimize noise.
  - Helped identify significant deviations in price movements.
- **7-day Rolling Standard Deviation**:
  - Measured volatility, showing variations in price stability over time.

### 4. Stationarity Testing
- Performed the **Augmented Dickey-Fuller (ADF) test** on both original and transformed data:
  - Test Statistic (Original): -1.512605.
  - Test Statistic (Transformed): -13.97091.
  - Critical Values: Stationarity confirmed at the 1% significance level after transformation.

### 5. Seasonal Decomposition
- Decomposed the log-transformed series using the **Seasonal Decompose** method:
  - Extracted **trend**, **seasonality**, and **residuals** components.
  - Analyzed residuals for stationarity to ensure no systematic patterns remained.

### 6. Correlation Analysis
- Computed **Autocorrelation Function (ACF)** and **Partial Autocorrelation Function (PACF)**:
  - **ACF**: Gradual decline in correlation, indicating lagging effects of prior values.
  - **PACF**: Sharp cutoffs after a few lags, characteristic of autoregressive processes.
  - Informed the choice of ARIMA parameters `(p=10, d=0, q=0)`.

---


## Models and Techniques
### 1. **ARIMA Model**
- Parameters: `(p=10, d=0, q=0)` based on ACF and PACF plots.
- Focus on long-term trend analysis and prediction.

### 2. **Gradient Boosting Regressor**
- Configurations: 100 estimators, learning rate of 0.1.
- Lower RMSE (743.90), indicating high predictive accuracy.

### 3. **Random Forest Regressor**
- Configurations: 100 estimators, max depth of 3.
- Higher RMSE (3774.71), indicating challenges in high volatility periods.

---

## Results
- **Short-term Forecasts**:
  ARIMA predicts prices for the next 7 days with reasonable accuracy.

- **Long-term Forecasts**:
  ARIMA extends predictions to a full year, highlighting potential trends.

- **Model Comparison**:
  Gradient Boosting outperformed Random Forest in precision but ARIMA was valuable for strategic, long-term insights.

---

## Discussion
- **Gradient Boosting**: Best suited for short-term trading strategies.
- **Random Forest**: Effective for capturing general trends.
- **ARIMA**: Ideal for strategic, long-term planning.

Continual model refinements are recommended due to the evolving nature of cryptocurrency markets.

---

## Summary
This project demonstrates the potential of machine learning and statistical methods in cryptocurrency analysis. The findings underline the importance of model selection based on specific objectives (e.g., trading vs. long-term investment).

---

## References
- [Investopedia: ARIMA Model](https://www.investopedia.com/terms/a/autoregressive-integrated-moving-average-arima.asp)
- [Medium: Bitcoin Price Prediction with Random Forest](https://medium.com/analytics-vidhya/bitcoin-price-prediction-with-random-forest-and-technical-indicators-python-560800d6f3cd)
- [ResearchGate: ARIMA Model Analysis](https://www.researchgate.net/publication/340566388_Bitcoin_Price_Prediction_using_ARIMA_Model)

---

