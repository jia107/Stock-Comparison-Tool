# Stock Comparison Tool

A Python-based Jupyter Notebook application that dynamically fetches historical stock data, calculates key performance metrics, and visualizes cumulative returns for comparison.

## Features
- **Interactive Ticker Input:** Prompts the user to enter any comma-separated stock symbols (e.g., `AAPL, MSFT, BTC-USD`).
- **Dynamic Data Retrieval:** Automatically fetches the past 5 years of historical price data via Yahoo Finance (`yfinance`).
- **Statistical Processing:** Extracts the Adjusted Closing prices to handle stock splits and dividends accurately.
- **Log Returns Calculation:** Computes daily log returns and transforms them into cumulative log returns to show total growth over time.

---

## Financial Logic Explained

Instead of using simple percentage returns, this tool utilizes **Log Returns** for analysis. 

### Why Log Returns?
1. **Time Additivity:** Log returns can be added across time intervals. For example, the log return over a week is simply the sum of the daily log returns for that week. 
2. **Mathematical Convenience:** Log returns are normally distributed more closely than simple returns, making them standard practice in algorithmic trading and portfolio analysis.

The tool calculates daily log returns using the following formula:
$$R_t = \ln\left(\frac{P_t}{P_{t-1}}\right)$$

And cumulative returns are computed by taking the cumulative sum ($cumsum$) of those daily log returns.

---

## Installation & Requirements

To run this project locally, clone the repository, navigate to the project directory, and install the dependencies using the included `requirements.txt` file:

```bash
pip install -r requirements.txt
How to Run
Open Compare stocks.ipynb inside VS Code or any Jupyter Notebook environment.

Run the cells sequentially.

Enter the target stock symbols when prompted in the console.
