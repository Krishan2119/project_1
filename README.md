# Trader Behavior vs Market Sentiment Analysis

##  Project Overview

This project investigates the relationship between **Bitcoin market sentiment** (Fear vs Greed) and **historical trader behavior from the Hyperliquid platform. The goal is to uncover behavioral patterns and performance metrics tied to sentiment-driven market conditions, ultimately enabling smarter trading strategies.

---

## Datasets Used

### 1. Bitcoin Market Sentiment Dataset
- Columns: `Date`, `classification` (Fear or Greed)
- Represents daily investor sentiment on the Bitcoin market.

### 2. Historical Trader Data from Hyperliquid
- Columns: 
  - `Account`, `Coin`, `Execution Price`, `Size Tokens`, `Size USD`, `Side`, 
  - `Timestamp IST`, `Start Position`, `Direction`, `Closed PnL`, `Transaction Hash`,
  - `Order ID`, `Crossed`, `Fee`, `Trade ID`, `Timestamp`
- Captures trade-level data from individual accounts including size, timing, and outcomes.

---

## Tools & Technologies

- Python-(Pandas, NumPy)
- Data Visualization: Matplotlib, Seaborn
- Jupyter Notebook for interactive analysis

---

##  Steps Performed

### 1. Data Cleaning & Preprocessing
- Parsed `Timestamp IST` to extract trade date.
- Ensured consistent date formats across both datasets.
- Handled null values and filtered out invalid rows.

```python
trader_df['Timestamp IST'] = pd.to_datetime(trader_df['Timestamp IST'], errors='coerce')
trader_df['Date'] = trader_df['Timestamp IST'].dt.date
sentiment_df['Date'] = pd.to_datetime(sentiment_df['Date']).dt.date
