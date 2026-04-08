# VECM–APARCH Trading Strategy (with Trend Filter)

This project implements a hybrid trading strategy combining Vector Error Correction Model for multivariate cointegration analysis with APARCH volatility modeling. The strategy incorporates a trend filter to optimize performance during bull markets.

**Strategy Overview:**

Entry Signal: Buy when VECM-APARCH hybrid forecast > current price
Exit Logic: Sell when forecast < price, but modified by market regime:
In downtrends: Exit immediately
In uptrends: Hold through small declines, exit only on elevated volatility
In ranging markets: Exit on sell signals
Assets: Multi-asset class correlation (Oil, Equity Futures, Currencies, Metals, Volatility)
Target: SPY (S&P 500 ETF)

## Performance Summary
This strategy showed strong out-of-sample performance in our test window, delivering higher cumulative and annualized returns than a SPY buy-and-hold benchmark, with a Sharpe ratio around 1 in the sample run. Overall, the VECM–APARCH + trend filter approach appears promising for capturing directional moves while managing exits across market regimes.

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


