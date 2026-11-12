# Portfolio Risk Analysis Using Python

A quantitative risk analysis project that evaluates the risk and historical performance of an equal-weighted portfolio of five NSE-listed stocks using Python.

## Project Overview

This project analyzes a hypothetical portfolio with an initial investment of **₹10,00,000**, equally distributed across five stocks from different sectors.

The analysis uses five years of historical daily stock price data to estimate portfolio risk, evaluate potential losses and assess model performance under historical and hypothetical adverse market conditions.

## Portfolio Composition

| Company | Sector | Portfolio Weight |
|---|---|---:|
| HDFC Bank | Banking | 20% |
| TCS | Information Technology | 20% |
| Hindustan Unilever | FMCG | 20% |
| Reliance Industries | Energy | 20% |
| Mahindra & Mahindra | Automobile | 20% |

## Technologies Used

- Python
- Pandas and NumPy
- yfinance
- Matplotlib and Seaborn
- SciPy
- Jupyter Notebook

## Risk Analysis and Methodologies

### 1. Exploratory Data Analysis
- Historical stock returns and volatility
- Stock return correlation analysis
- Portfolio construction and volatility measurement

### 2. Value at Risk (VaR)
Implemented three VaR methodologies at 95% and 99% confidence levels:

- Parametric VaR
- Historical VaR
- Monte Carlo VaR using 10,000 simulations

### 3. Expected Shortfall (ES)
Estimated average portfolio losses beyond the Historical VaR thresholds.

### 4. VaR Backtesting
- Rolling Historical VaR using a 250-trading-day estimation window
- Identification and analysis of VaR violations
- Kupiec Proportion of Failures (POF) test

### 5. Stress Testing
Evaluated portfolio losses under three hypothetical scenarios:
- Market Crash
- Moderate Downturn
- Sector-Specific Shock

## Key Results

| Risk Measure | 95% Confidence | 99% Confidence |
|---|---:|---:|
| Parametric VaR | ₹15,354.18 | ₹21,838.68 |
| Historical VaR | ₹15,245.95 | ₹23,224.73 |
| Monte Carlo VaR | ₹15,460.82 | ₹22,164.40 |
| Historical Expected Shortfall | ₹20,558.86 | ₹29,810.81 |

### Backtesting Results

- 95% VaR violation rate: 5.89%
- 99% VaR violation rate: 1.52%
- Kupiec POF test p-values: 0.2128 (95%) and 0.1257 (99%)

Both p-values exceeded the 0.05 significance level, indicating that the observed violation frequencies were statistically consistent with the expected frequencies.

## Project Structure

```text
portfolio-risk-analysis/
│
├── portfolio_risk_analysis.ipynb
└── README.md
```

## Data Source

Historical stock price data was collected using the Yahoo Finance API through the `yfinance` Python library.

## How to Run

1. Clone this repository.
2. Install the required libraries:

```bash
pip install pandas numpy yfinance matplotlib seaborn scipy jupyter
```

3. Launch Jupyter Notebook:

```bash
jupyter notebook
```

4. Open `portfolio_risk_analysis.ipynb` and run the cells.

## Disclaimer

This project is for educational and analytical purposes only. Historical data and hypothetical stress scenarios do not predict future market performance. The risk estimates depend on the assumptions and limitations of the selected methodologies.
