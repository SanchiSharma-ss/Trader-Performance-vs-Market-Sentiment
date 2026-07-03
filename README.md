# Trader Performance vs Market Sentiment Analysis

## Project Overview

This project investigates the relationship between **Bitcoin market sentiment** (Fear & Greed Index) and **trader behavior** on the Hyperliquid exchange.

The objective is to determine whether market sentiment influences trader performance, trading activity, and trading behavior, and to identify patterns that could contribute to smarter trading strategies.

The project follows a complete data analytics workflow including data preparation, feature engineering, exploratory data analysis, and business insight generation.

---

## Project Objectives

The analysis aims to answer the following business questions:

1. Does trader performance (PnL, Win Rate, Drawdown Proxy) differ between Fear and Greed market conditions?
2. Do traders change their behavior based on market sentiment?
   - Trade Frequency
   - Position Size
   - Long vs Short Bias
3. Can traders be segmented based on their trading characteristics?
   - Frequent vs Infrequent Traders
   - Consistent vs Inconsistent Winners

---

## Dataset Description

### 1. Bitcoin Fear & Greed Index

Contains the daily Bitcoin market sentiment.

Columns include:

- Date
- Fear & Greed Value
- Classification
  - Extreme Fear
  - Fear
  - Neutral
  - Greed
  - Extreme Greed

---

### 2. Hyperliquid Historical Trader Data

Contains historical trading activity on Hyperliquid.

Key columns include:

- Account
- Coin
- Execution Price
- Trade Size (USD)
- Side
- Direction
- Closed PnL
- Timestamp
- Transaction Hash

---

## Project Structure

```
Trader_Performance_vs_Market_Sentiment/
│
├── data/
│   ├── raw/
│   │   ├── historical_data.csv
│   │   └── fear_greed_index.csv
│   │
│   └── processed/
│       ├── average_trade_size_per_trader.csv
│       ├── daily_average_pnl.csv
│       ├── daily_pnl.csv
│       ├── daily_total_pnl.csv
│       ├── daily_trading_volume.csv
│       ├── open_positions.csv
│       ├── trade_count_per_trader.csv
│       ├── trade_count.csv
│       ├──trader_sentiment_engineered.csv
│       ├──trader_sentiment_processed.csv 
│       ├── trades_per_day.csv
│       └── win_rate_per_trader.csv
│ 
├── notebooks/
│   ├── 01_Data_Preparation.ipynb
│   ├── 02_Feature_Engineering.ipynb
│   └── 03_Exploratory_Data_Analysis.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Methodology

### 1. Data Preparation

- Loaded both datasets
- Checked dataset dimensions
- Verified data types
- Handled missing values
- Removed duplicate records
- Converted timestamps to datetime format
- Merged trader data with daily sentiment data
- Saved processed dataset

---

### 2. Feature Engineering

The following features were created:

- Win Indicator
- Win Rate per Trader
- Trade Count per Trader
- Average Trade Size per Trader
- Daily PnL
- Daily Trading Volume
- Daily Average PnL
- Daily Total PnL
- Trades per Day
- Open Positions
- Position Type

---

### 3. Exploratory Data Analysis

The following analyses were performed:

### Trader Performance

- Average PnL by Market Sentiment
- Total PnL by Market Sentiment
- Win Rate by Market Sentiment
- Drawdown Proxy

### Trader Behavior

- Trade Frequency
- Average Position Size
- Long vs Short Bias

### Trader Segmentation

- Frequent vs Infrequent Traders
- Consistent vs Inconsistent Winners

---

## Key Findings

- Trading performance differs across market sentiment conditions.
- Traders modify their directional bias according to market sentiment.
- Trading activity changes during Fear and Greed periods.
- Frequent traders achieve slightly higher win rates than infrequent traders.
- Consistent winners significantly outperform inconsistent traders.

---

## Limitations

- The dataset does not include leverage information.
- True drawdown cannot be calculated due to the absence of account equity.
- Analysis is limited to realized PnL.
- The Fear & Greed Index represents overall Bitcoin market sentiment and may not reflect sentiment for every traded asset.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## How to Run

1. Clone this repository.

```bash
git clone <repository-url>
```

2. Install dependencies.

```bash
pip install -r requirements.txt
```

3. Open Jupyter Notebook.

```bash
jupyter notebook
```

4. Execute notebooks in the following order:

```
01_Data_Preparation.ipynb

↓

02_Feature_Engineering.ipynb

↓

03_Exploratory_Data_Analysis.ipynb
```

---

## Future Work

Possible extensions of this project include:

- Incorporating actual leverage information.
- Integrating Bitcoin price data.
- Computing true portfolio drawdown.
- Building predictive machine learning models.
- Performing time-series forecasting using sentiment indicators.

---
# Project Summary

## Methodology

This project follows a structured data analytics workflow to investigate the relationship between Bitcoin market sentiment and trader performance on Hyperliquid.

The analysis consisted of three stages:

1. **Data Preparation**
   - Loaded and inspected the Fear & Greed Index and Hyperliquid trading datasets.
   - Handled missing values and duplicate records.
   - Converted timestamps into a common date format.
   - Merged both datasets on daily dates to associate each trade with the prevailing market sentiment.

2. **Feature Engineering**
   - Created trader-level and daily-level features including:
     - Daily Profit & Loss (PnL)
     - Win Rate
     - Average Trade Size
     - Trade Count
     - Daily Trading Volume
     - Open Position indicators
     - Position Type (Opening / Closing)

3. **Exploratory Data Analysis**
   - Compared trader performance across different market sentiment categories.
   - Examined changes in trading behavior, including trade frequency, position sizes, and long/short bias.
   - Segmented traders into Frequent vs. Infrequent Traders and Consistent vs. Inconsistent Winners to identify behavioral differences.

---

## Key Insights

- Traders generally achieved higher realized profitability during Greed and Extreme Greed market conditions compared with Fear periods.
- Trading activity increased during stronger market sentiment (Fear and Greed) relative to Neutral conditions.
- Trader positioning changed with sentiment, with long positions becoming more common during optimistic markets.
- Frequent traders demonstrated slightly higher average win rates than infrequent traders.
- Consistent winners substantially outperformed inconsistent traders, highlighting clear differences in trading effectiveness.

---

## Strategy Recommendations

Based on the analysis, the following practical recommendations can be made:

- **Incorporate market sentiment into trading decisions**, as trader performance and behavior vary across sentiment conditions.
- **Monitor trade frequency during high-emotion markets**, since trading activity increases significantly during Fear and Greed periods.
- **Evaluate trader consistency rather than only total profitability**, as consistently profitable traders exhibit stronger long-term performance characteristics.
- **Use sentiment as a complementary indicator** alongside technical and risk management strategies rather than relying on it in isolation.

Overall, the analysis demonstrates that market sentiment provides valuable context for understanding trader behavior and can contribute to more informed trading strategies.

## Author

**Sanchi Sharma**

Computer Science Engineering Student

Aspiring Data Analyst | Machine Learning Engineer

GitHub: https://github.com/SanchiSharma-ss

LinkedIn: https://www.linkedin.com/in/sanchisharma21
