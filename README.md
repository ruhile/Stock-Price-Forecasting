# Week 16: Stock Price Forecasting

## Project Overview
This project focuses on Dataset exploration, Exploratory Data Analysis (EDA), Feature Engineering, Machine Learning Modeling, and Time Series Forecasting with ARIMA for Apple Inc. (`AAPL`) historical stock data from Yahoo Finance via `yfinance`.

## Project Structure
```text
Week16_Stock_Price_Forecasting/
│
├── data/
│   ├── AAPL_raw.csv
│   ├── AAPL_eda.csv
│   ├── AAPL_features.csv
│   └── processed_stock_data.csv
├── notebooks/
│   ├── stock_forecasting.ipynb
│   ├── stock_eda.ipynb
│   ├── feature_engineering.ipynb
│   ├── stock_forecasting_model.ipynb
│   └── arima_forecasting.ipynb
├── images/
│   ├── apple_closing_price.png
│   ├── eda_closing_price.png
│   ├── eda_trading_volume.png
│   ├── eda_high_vs_low.png
│   ├── eda_daily_returns.png
│   ├── eda_daily_returns_distribution.png
│   ├── eda_moving_averages.png
│   ├── eda_rolling_std.png
│   ├── eda_correlation_heatmap.png
│   ├── actual_vs_predicted.png
│   ├── arima_train_test.png
│   ├── arima_forecast_vs_actual.png
│   ├── arima_full_forecast.png
│   └── arima_30day_forecast.png
├── model/
│   └── linear_regression_stock.pkl
├── report/
├── README.md
└── requirements.txt
```

## Daily Progress & Checklists

### Day 1: Dataset & Time Series Basics
- Initialized folder structure and dependencies (`yfinance`, `pandas`, `matplotlib`, `seaborn`).
- Fetched AAPL historical data from 2018-01-01 to 2026-01-01.
- Verified `DatetimeIndex` and explored dataset structure (`info()`, `describe()`, `shape`).

### Day 2: Exploratory Data Analysis (EDA)
- Analyzed price trends, trading volume, and high vs low spreads.
- Computed daily returns and return distribution plots.
- Calculated 20-day & 50-day Moving Averages (`MA20`, `MA50`) and rolling volatility (`STD20`).
- Generated feature correlation heatmaps.

### Day 3: Feature Engineering for Time Series
- Engineered 1, 2, 3, 5, and 10-day lag features (`Lag_1` to `Lag_10`).
- Created moving averages (`MA10`, `MA20`, `MA50`) and rolling standard deviations (`STD20`).
- Calculated daily returns, rolling return averages (`Return_MA10`), and return volatility (`Return_STD10`).
- Cleaned missing values (`dropna()`) and saved final dataset to `data/processed_stock_data.csv`.

### Day 4: Build Baseline Stock Price Forecasting Model
- Loaded `processed_stock_data.csv` and created target column `Target = Close.shift(-1)`.
- Performed sequential time series split (`train_test_split(shuffle=False)` with 80% train / 20% test).
- Trained **Linear Regression** baseline model.
- Evaluation Metrics:
  - **MAE:** `2.9090`
  - **RMSE:** `4.1947`
  - **R² Score:** `0.9653`
- Visualized Actual vs Predicted price trend chart ([images/actual_vs_predicted.png](file:///c:/Users/acer/Desktop/python/week16/Week16_Stock_Price_Forecasting/images/actual_vs_predicted.png)).
- Predicted next trading day closing price: `$273.37`.
- Exported trained model artifact to `model/linear_regression_stock.pkl`.

### Day 5: Time Series Forecasting with ARIMA
- Built & fitted an **ARIMA(5, 1, 0)** model on historical training data.
- Evaluated test multi-step forecast performance (`MAE: 36.6161`, `RMSE: 42.7866`).
- Fitted full dataset and generated 30-day future stock price forecast ([images/arima_30day_forecast.png](file:///c:/Users/acer/Desktop/python/week16/Week16_Stock_Price_Forecasting/images/arima_30day_forecast.png)).

| Model | Advantages | Limitations |
| :--- | :--- | :--- |
| **Linear Regression** | Fast, simple, highly accurate with multi-feature lag inputs | Requires engineered lag features; doesn't natively model residual autocorrelation |
| **ARIMA** | Native time series model; handles trends & autoregression without exogenous features | Multi-step unguided forecasts regress toward mean; sensitive to non-stationarity |

## Setup & Installation

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Run Jupyter Notebooks:
```bash
jupyter notebook notebooks/arima_forecasting.ipynb
```
