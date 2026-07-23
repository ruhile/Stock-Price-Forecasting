# Week 16: Stock Price Forecasting

## Project Overview
This project focuses on Dataset & Time Series Basics for stock price forecasting using Apple Inc. (`AAPL`) historical data from Yahoo Finance via the `yfinance` library.

## Project Structure
```text
Week16_Stock_Price_Forecasting/
│
├── data/               # Contains raw and processed dataset files
├── notebooks/          # Jupyter notebooks for analysis and modeling
├── images/             # Generated charts and visualization figures
├── report/             # Summary reports and insights
├── README.md           # Project documentation
└── requirements.txt    # Python dependencies
```

## Setup & Installation

1. Install the required Python packages:
```bash
pip install -r requirements.txt
```

2. Run the Jupyter Notebook:
```bash
jupyter notebook notebooks/stock_forecasting.ipynb
```

## Dataset
- **Ticker:** AAPL (Apple Inc.)
- **Date Range:** 2018-01-01 to 2026-01-01
- **Source:** Yahoo Finance (`yfinance`)
- **Key Columns:** Date, Open, High, Low, Close, Volume
