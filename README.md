# Bitcoin Regime Detection (Machine Learning)

This project analyzes Bitcoin market behavior by detecting structural volatility regimes using daily returns, rolling volatility, and trend-based features.

---

## Methodology

**Features Used**
- Daily Returns
- 30-Day Rolling Volatility
- 30-Day Trend

**Model**
- StandardScaler for normalization
- K-Means clustering (3 regimes)

**Output**
- Bull, Neutral, Bear regimes
- Regime-based strategy logic
- Backtested performance metrics (Sharpe, Drawdown, Win Rate)

---

## Notebook
`Bitcoin_Regime_Model.ipynb`
