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
1. **ARIMA Model**:
   - Log transformation and differencing for stationarity.
   - Exponential Weighted Moving Average (EWMA) for trend analysis.

2. **Random Forest and Gradient Boosting**:
   - Forward filling for missing data.
   - Feature engineering for date-based trends.

---

## Data Exploration
- Visualization of price trends over time to identify volatility and patterns.
- Rolling averages and statistical tests like Dickey-Fuller for stationarity.

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

Feel free to contribute or raise issues!
