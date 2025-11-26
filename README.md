# Market Regime Classification for Bitcoin (BTC-USD)

**Author:** Swathi Pokuri  
**Focus:** Quantitative Research, Statistical Modeling, ML for Financial Markets  
**Tech Stack:** Python (Pandas, NumPy, scikit-learn, Matplotlib), yfinance  

---

## Overview

This repository contains a complete market regime classification framework for Bitcoin using unsupervised learning.  
The objective is to identify statistically distinct market regimes and evaluate the impact of regime-conditioned exposure on performance relative to a passive benchmark.

The project follows a workflow consistent with institutional quantitative research practices:  
feature construction → standardization → clustering → diagnostics → strategy design → performance evaluation.

---

## Project Structure

- **BTC_Regime_Model.ipynb** — full research notebook (data, models, diagnostics, backtest)  
- **README.md** — documentation and methodology  
- **/images** *(optional)* — saved figures (equity curve, regime profiles, diagnostics)

---

## Methodology

### Data
- Daily OHLCV for BTC-USD from 2016 onward  
- Source: Yahoo Finance  

### Feature Set
Features reflect three orthogonal dimensions of market behavior:
- **Returns:** daily log returns  
- **Volatility:** 30-day realized volatility  
- **Trend:** 30-day momentum  

### Preprocessing
- Z-score standardization  
- NA removal  
- Exploratory validation (distributional + correlation analysis)

### Regime Classification
Unsupervised segmentation using **K-Means (K = 3)** to identify:
1. Trending/Bullish regime  
2. Low-volatility/Neutral regime  
3. High-volatility/Stressed regime  

### Diagnostics
- Regime transition matrix (Markov-style persistence)  
- Cluster centroids in standardized space  
- Silhouette score for cluster separation  
- Regime-specific statistical summaries  

### Strategy Logic
A simple regime-aware allocation model:
- **Long** during bullish regime  
- **Flat** during neutral regime  
- **Short** during stressed regime  

This model is illustrative and not optimized; its purpose is to evaluate the informational content of the regime labels.

### Performance Evaluation
Performance is assessed using institutional metrics:
- Annualized return (CAGR)  
- Annualized volatility  
- Sharpe ratio  
- Maximum drawdown  
- Hit rate (win rate)  
- Comparative equity curves vs. Buy & Hold  

---

## Key Findings

- The clustering algorithm consistently identifies three distinct BTC regimes with coherent economic interpretation.  
- Regimes exhibit non-random persistence, validating their potential use as a conditioning signal.  
- A naive regime-aware long/short allocation improves risk-adjusted performance relative to Buy & Hold, particularly by reducing drawdowns during stressed regimes.  
- The framework is modular and can be extended to multi-asset settings or more advanced models (e.g., HMMs, regime-switching volatility models).

---

## Extensions

Potential extensions for further research include:

- Hidden Markov Models for probabilistic regime estimation  
- Cross-asset regime alignment (BTC vs. SPX, NDX, ETH)  
- Regime-conditioned volatility targeting  
- Regime-specific return distribution fitting  
- Multi-regime portfolio allocation strategies  

---

## Contact

For quantitative research collaboration or discussion:  
**GitHub:** https://github.com/Spokuri2003
