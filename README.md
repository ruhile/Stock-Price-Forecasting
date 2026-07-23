# Week 16: Stock Price Forecasting

## Project Overview
This project focuses on Dataset, EDA, and Feature Engineering for stock price forecasting using Apple Inc. (`AAPL`) historical data from Yahoo Finance via `yfinance`.

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
│   └── feature_engineering.ipynb
├── images/
│   ├── apple_closing_price.png
│   ├── eda_closing_price.png
│   ├── eda_trading_volume.png
│   ├── eda_high_vs_low.png
│   ├── eda_daily_returns.png
│   ├── eda_daily_returns_distribution.png
│   ├── eda_moving_averages.png
│   ├── eda_rolling_std.png
│   └── eda_correlation_heatmap.png
├── report/
├── README.md
└── requirements.txt
```

## Daily Progress

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
- Cleaned missing values (`dropna()`) and saved the final processed dataset to `data/processed_stock_data.csv` `(1962 rows x 17 columns)`.

## Setup & Installation

1. Install requirements:
```bash
pip install -r requirements.txt
```

2. Run Jupyter Notebooks:
```bash
jupyter notebook notebooks/feature_engineering.ipynb
```
