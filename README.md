Trader Performance vs. Bitcoin Market Sentiment

Analysis of the relationship between Hyperliquid trader behavior/performance and the Bitcoin Fear & Greed Index — submitted as the Round-0 task for the Primetrade.ai AI Internship.

Datasets
Bitcoin Fear & Greed Index — daily sentiment classification (Fear, Greed, Extreme Fear/Greed, Neutral)
Hyperliquid Historical Trader Data — 211,224 trade-level records across 32 accounts (May 2023 – May 2025)
Approach
Joined trades to daily sentiment via date (99.997% match rate)
Computed profitability, win rate, and directional-bias metrics by sentiment regime
Ran a robustness check: initial pooled (trade-level) results were compared against equal-weighted (per-account) results, since 3 of 32 accounts drove 43% of total PnL. Some pooled patterns (e.g. an apparent Long/Short contrarian signal) did not hold up at the account level and were flagged/corrected rather than reported at face value.
Verified statistical significance with a one-way ANOVA (robust to outlier winsorizing)
Key Findings
Win rate and average per-trade profit are both highest during Greed/Extreme Greed (84-85% win rate) and lowest during Fear/Neutral — the opposite of the "calm markets are safest" intuition.
Differences in Closed PnL across sentiment regimes are statistically significant (ANOVA F=7.74, p<0.0001).
An initial pooled-data Long/Short "contrarian" pattern (69% Long in Extreme Fear vs. 45% in Extreme Greed) did not replicate at the per-account level (54% vs 53%) — documented as a robustness lesson rather than a false headline finding.

Full write-up with charts and methodology: Trader_Sentiment_Analysis_Report.docx

Repo Structure
├── trader_sentiment_analysis.py   # reproducible analysis pipeline
├── Trader_Sentiment_Analysis_Report.docx   # full report with charts & insights
├── chart1_avg_pnl_eq.png, chart2_win_rate_eq.png, chart3_long_short.png, chart4_trade_size.png
└── requirements.txt
Running it
bash
pip install -r requirements.txt
python trader_sentiment_analysis.py

Place historical_data.csv and fear_greed_index.csv in the same directory before running.

Author

Kumari Pratibha Mani — github.com/pratibha2617
