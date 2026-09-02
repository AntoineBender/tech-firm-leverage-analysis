# Tech Firm Leverage — Cross-Sectional Analysis

Does a technology company's debt load predict its stock performance or risk?
Cross-sectional study of 400 S&P 500 tech firms, pulled from Yahoo Finance,
examining whether Debt-to-Equity ratio correlates with return, risk (return
volatility), or size (revenue).

**Course:** Data Handling, IÉSEG School of Management — Prof. Hicham Daher
**Team:** Antoine Bender, Cyprien Carliez, Aglaé Guichard, Lou Rabache
**Period:** Sep – Nov 2025

## Method

- Pulled Ticker, long-term Debt-to-Equity, annualized return, return volatility
  (risk) and revenue for 400 S&P 500 tech-sector firms via `yfinance`
  (close of Dec 31, 2024; daily prices over 2024 for return/risk).
- Cleaned nulls and removed outliers with the 1.5×IQR method (D/E ratio had
  extreme outliers — max 1,888%). n = 344 after cleaning.
- Visualized: D/E boxplot (with outliers), D/E histogram (outliers removed),
  and three scatter plots (D/E vs. Revenue, vs. Risk, vs. Return), each
  annotated with its correlation coefficient.
- Split into two notebooks for performance: one to extract/cache the raw
  Yahoo Finance pull, one to clean, analyze and visualize.

## Files

- `debt_equity_report.pdf` — final 7-page report
- `debt_equity_analysis.ipynb` / `.pdf` — the analysis notebook (code,
  outputs, and charts) and its rendered PDF
- `data_extraction.ipynb` — the Yahoo Finance extraction notebook
- `debt_equity_data.csv` — the cleaned dataset

## Result

No significant correlation between Debt-to-Equity and Revenue (r ≈ -0.06),
Risk (r ≈ -0.05), or Return (r ≈ -0.05) across the sample. Leverage isn't a
systematic function of firm size in tech, and capital structure doesn't
predict stock performance or volatility in this sector/period — so a tech
firm's D/E ratio alone is not a useful signal for stock safety or
profitability.
