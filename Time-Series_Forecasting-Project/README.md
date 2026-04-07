# 📈 Predictive Sales Analytics: A SARIMAX Approach with Exogenous Marketing Data

This project implements a sophisticated time-series forecasting engine designed to predict daily retail sales. By leveraging **SARIMAX** (Seasonal AutoRegressive Integrated Moving Average with eXogenous factors), the model doesn't just look at past sales; it mathematically accounts for **Marketing Spend** as a leading indicator of revenue.

## 🚀 Project Overview
The core objective was to move beyond simple "trend-following" and create a model that understands the **causal relationship** between marketing activity and consumer behavior.

### Key Features:
* **Exogenous Variables**: Integrated `marketing_spend` with a 2-day lag to capture the "delay effect" of advertising on sales.
* **Seasonality Handling**: Built-in 7-day seasonal differencing to account for weekly retail cycles.
* **Statistical Validation**: Full suite of tests including **ADF (Stationarity)**, **Granger Causality**, and **Ljung-Box (Residual analysis)**.
* **Tournament Selection**: Automated comparison of multiple model architectures based on **AIC** and **BIC** metrics.

---

## 🛠️ The Data Science Pipeline

### 1. Exploratory Data Analysis (EDA)
Identified a clear upward trend and a strong 7-day seasonal "heartbeat." Visualized the correlation between marketing pulses and subsequent sales spikes.

### 2. Stationarity & Transformation
Applied first-order and seasonal differencing ($d=1, D=1$) to stabilize the mean and variance. Confirmed results using the **Augmented Dickey-Fuller (ADF) test**.

### 3. Granger Causality

Statistically proved that **Marketing Spend** "Granger-causes" **Sales**. This validated the decision to treat marketing as an **Exogenous (X)** feature rather than just a correlated variable.

### 4. Model Selection (The Tournament)
Evaluated 5 different candidate models. The **SARIMAX(1,1,1)(2,1,2)[7]** emerged as the winner, offering the best balance of accuracy and simplicity.

### 5. Diagnostic Health Check

Used Residual Diagnostics (Q-Q plots and Histograms) to ensure prediction errors were normally distributed. The **Ljung-Box test** confirmed that the model successfully captured the primary data patterns.

---

## 📊 Performance Metrics
The model was put through a 5-fold **Time Series Cross-Validation** stress test:
* **Average MAPE**: 2.74% (97.26% Accuracy)
* **Pseudo R²**: High variance explanation of sales movements.
* **Confidence Interval**: 95% "Uncertainty Funnel" for risk-managed forecasting.

---

## 🔮 Future Forecasting
The repository includes a 14-day look-ahead forecast. The model dynamically adjusts the "Uncertainty Cloud" as it predicts further into the future, providing a realistic range for business planning.

---

### 🧰 Tech Stack
* **Python**: Core logic
* **Statsmodels**: SARIMAX engine and statistical testing
* **Pandas/NumPy**: Data manipulation
* **Matplotlib/Seaborn**: Technical visualizations
