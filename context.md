# Python Data Analysis Project — Cross-sectional study of tech firm leverage

**Course:** Data Handling (IÉSEG, 3A / S4), Prof. Hicham Daher
**Team:** "Ace Research and Consulting Co", Group 3 — Antoine Bender, Cyprien Carliez, Aglaé Guichard, Lou Rabache
**Dates:** Sep 2025 (kickoff, Sep 17) – Nov 4 2025 (submission)
**Files in this folder:** `DHS4_Report_Bender_Carliez_Rabache_Guichard.pdf` (final 7-page report), `DHS4_Data_Bender_Carliez_Guichard_Rabache.csv` (raw dataset)

## Research question
Is there a relationship between a company's debt financing level (Debt-to-Equity ratio) and its financial performance (stock return), size (revenue), and risk (volatility of returns)?

## Method
- Pulled financial data for 400 publicly listed S&P 500 companies from Yahoo Finance via a Python script (`yfinance` library), closing date Dec 31, 2024; daily prices over all of 2024 for return/risk calcs.
- Restricted sample to the technology sector for comparability (D/E ratios vary a lot cross-industry).
- 5 variables: Ticker, Long-term Debt-to-Equity Ratio (%), Risk (std dev of annualized daily returns), Rate of Return (annualized), Revenue.
- Cleaning: dropped incomplete rows (`dropna()`), removed outliers via 1.5×IQR method (D/E ratio had extreme outliers, e.g. max 1888%).
- Split workload into two notebooks for performance: one to extract/save raw CSV from Yahoo Finance, one to clean/transform/visualize (both were built in Google Colab; not saved locally — only the raw CSV and final PDF survived on this machine).
- Visualizations: boxplot (D/E with outliers), histogram of D/E without outliers, 3 scatter plots (D/E vs Revenue, vs Risk, vs Return) each annotated with correlation coefficient.
- AI disclosure: used Gemini (in Colab) only to add correlation-value text annotations on scatter plots (lines 44–53); all outputs reviewed/verified by the team.

## Core stats (n=344 after cleaning)
| | Debt/Equity | Risk | Return | Revenue |
|---|---|---|---|---|
| mean | 129.2% | 0.336 | 9.5% | $39.3B |
| std | 181.6 | 0.135 | 0.359 | $80.6B |
| median | 75.6% | 0.302 | 6.4% | $14.4B |

## Key finding
**No significant correlation** between Debt-to-Equity and any of Revenue (r ≈ -0.06), Risk (r ≈ -0.05), or Return (r ≈ -0.05).

Interpretation: leverage isn't a systematic function of firm size in tech, and capital structure doesn't predict stock performance or volatility in this sector/period.

## Recommendation drawn in the report
Don't use a tech firm's Debt-to-Equity ratio as a signal for stock safety or profitability — the data shows no consistent link between leverage and either risk or return, nor between firm size and leverage.

## Notable challenge (good interview/story material)
Initially worried a null result meant the analysis "wasn't interesting" and considered swapping variables to force a correlation — then reframed: demonstrating the *absence* of a relationship is itself a valid, useful insight (directly counters a common investor assumption). Also solved a performance problem by splitting data-extraction and analysis into separate notebooks after the all-in-one version became too slow pulling 400 tickers × 4 variables each run.

## Usage notes for outreach/interviews
- This is the project referenced in [profile/cv.md](../cv.md) under "Leadership & projects".
- Good hook for: quant/data-driven roles, equity research, credit/leverage-focused groups, or any conversation about capital structure.
- Antoine can speak to: the null-result framing, S&P 500 data sourcing via yfinance, IQR outlier handling, and the group's methodology split for performance.
