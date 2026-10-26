
## Version 2  Historical Market Data Integration

### Overview

Updated the original mean-variance portfolio optimization model to use real historical stock market data instead of simulated stock returns.

### New Features

- Integrated historical adjusted closing price data from Yahoo Finance.
- Added automated historical data retrieval for AAPL, MSFT, NVDA, AMZN, and GOOGL.
- Calculated daily historical stock returns.
- Calculated annualized arithmetic expected returns.
- Calculated annualized covariance matrices.
- Added compounded annual growth rate (CAGR) calculations.
- Updated Monte Carlo portfolio simulations to use historical market data.
- Added an approximate efficient frontier based on simulated portfolio allocations.
- Updated portfolio Sharpe ratio and Capital Market Line calculations using a Treasury-based risk-free rate assumption.

### Methodology

Daily returns are calculated from adjusted closing prices.

Annualized expected returns are estimated using the arithmetic mean of daily returns multiplied by 252 trading days.

The annualized covariance matrix is calculated by multiplying the daily covariance matrix by 252.

CAGR is calculated using the beginning and ending adjusted prices over the historical measurement period.

### Limitations

- Historical returns do not guarantee future performance.
- The efficient frontier is currently approximated using Monte Carlo simulation rather than exact constrained optimization.
- The risk-free rate is an input that should be updated as Treasury yields change.
- Expected returns are sensitive to the selected historical period.

### Next Development Goals

- Implement exact constrained portfolio optimization.
- Add historical portfolio backtesting.
- Incorporate transaction costs.
- Add Value at Risk (VaR) and Conditional Value at Risk (CVaR).
- Develop an interactive MATLAB dashboard.



# Mean-Variance-Portfolio-Optimization
MATLAB implementation of Monte Carlo portfolio simulation and Modern Portfolio Theory optimization.

Overview

This project implements a quantitative portfolio optimization model in MATLAB using Modern Portfolio Theory (MPT), Monte Carlo simulation, and covariance-based risk analysis.

The objective is to evaluate different asset allocations and identify portfolios that optimize the relationship between expected return and risk.

# Key Features:
Monte Carlo simulation of 15,000 randomly generated portfolios.

Expected portfolio return calculations.

Covariance-based portfolio variance and volatility calculations.

Sharpe ratio calculations for risk-adjusted performance.

Minimum-variance portfolio optimization.

Tangency portfolio identification.

Efficient frontier visualization.

Capital Market Line visualization.

Individual asset risk and return comparisons.

# Mathematical Framework
Expected Portfolio Return

E(Rp) = wᵀμ

Portfolio Variance

σ²p = wᵀΣw

Portfolio Standard Deviation

σp = √(wᵀΣw)

Sharpe Ratio

S = (E(Rp) - Rf) / σp

Where:

w = Portfolio weight vector

μ = Expected asset return vector

Σ = Covariance matrix

Rf = Risk-free rate

σp = Portfolio standard deviation

# Optimization Methodology
The minimum-variance portfolio is calculated using MATLAB's built-in fminsearch function.

A softmax transformation converts unrestricted optimization variables into positive portfolio weights that sum to one, enforcing long-only and fully invested portfolio constraints.

The tangency portfolio is approximated through Monte Carlo sampling by selecting the simulated portfolio with the highest Sharpe ratio.

# Visualization

The visualization includes:

Monte Carlo simulated portfolios

Efficient frontier

Minimum-variance portfolio

Maximum-Sharpe tangency portfolio

Capital Market Line

Individual asset risk and return positions

# Limitations
The initial implementation uses simulated asset returns rather than historical market data.

The Monte Carlo tangency portfolio is an approximation and is not guaranteed to represent the global maximum-Sharpe portfolio.

The model currently excludes transaction costs, taxes, and market impact.

# Future Improvements
Incorporate historical financial market data.

Implement out-of-sample backtesting.

Compare covariance estimation methods.

Incorporate transaction costs.

Evaluate maximum drawdown and portfolio performance against benchmarks.
