# Trader Performance vs Market Sentiment

## Overview
Analysis of how Bitcoin market sentiment (Fear/Greed Index) 
relates to trader behavior and performance on Hyperliquid DEX.

## Setup
```bash
pip install -r requirements.txt
```

## How to Run
1. Clone the repo
2. Place datasets in `/data` folder:
   - `fear_greed_index.csv`
   - `historical_data.csv`
3. Open `notebooks/trader-sentiment-analysis.ipynb`
4. Run all cells top to bottom

## Project Structure
```
trader-sentiment/
├── data/                  # Raw CSV datasets
├── notebooks/             # Main analysis notebook
├── charts/                # All output charts & tables
├── README.md
└── requirements.txt
```

## Methodology
- Merged Fear/Greed sentiment index with Hyperliquid 
  trade-level data on daily date key
- Engineered per-trader daily metrics: PnL, win rate, 
  trade frequency, position size, long/short ratio
- Segmented traders by frequency and win-rate consistency
- Ran Mann-Whitney U tests to validate PnL differences

## Key Insights
1. **Greed days trend toward higher PnL** (p=0.06) — 
   a near-significant signal that sentiment influences returns
2. **Trader behavior shifts by sentiment** — win rates and 
   long ratios differ meaningfully across Fear/Neutral/Greed
3. **Consistent winners outperform on all sentiment days** — 
   win-rate segment is a stronger predictor than sentiment alone

## Strategy Recommendations
**Rule 1:** Reduce position size during Fear days — 
PnL trends lower across all trader segments.

**Rule 2:** Use win-rate as a trader quality filter — 
consistent winners maintain positive PnL regardless of sentiment, 
making them resilient to market mood shifts.

## Datasets
- Bitcoin Fear/Greed Index (2018–2025)
- Hyperliquid Historical Trader Data