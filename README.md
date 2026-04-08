# VECM–APARCH Trading Strategy (with Trend Filter)

A research-style trading prototype that combines **VECM** (for multivariate mean dynamics / cointegration structure) and **APARCH** (for volatility dynamics), with a simple **trend filter** for position management.


## Project Objective

Build and evaluate a hybrid, walk-forward strategy that forecasts SPY direction using signals from a multi-asset feature set:
- Crude Oil (`CL=F`)
- Dow Futures (`YM=F`)
- Nasdaq Futures (`NQ=F`)
- Dollar Index (`DX-Y.NYB`)
- Gold (`GC=F`)
- Natural Gas (`NG=F`)
- VIX (`^VIX`)
- Target: `SPY`

## Method Summary

1. Download daily market data with `yfinance`
2. Split into train/test
3. Fit VECM on training history
4. Fit APARCH on target residual dynamics
5. Generate hybrid forecast in walk-forward loop
6. Apply trend-aware trading logic:
   - Buy if forecast > price
   - Sell if forecast < price, with trend/volatility conditions
7. Compare against Buy & Hold benchmark


## Current Backtest Assumptions

- Daily bars (`1d`)
- No transaction costs/slippage/market impact
- Long-only, no leverage constraints
- Walk-forward model re-fitting

## Limitations

- Hybrid forecast combination is experimental and not fully standardized
- No explicit transaction cost or slippage model
- APARCH order search space is small
- Limited robustness testing across regimes and parameter perturbations

## Further Improvements

1. Add transaction costs and slippage
2. Including position sizing
3. Adding risk controls


