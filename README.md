# MLB Team Win Total Forecasting Model
Forecasts MLB team win totals by aggregating individual player projections into team-level metrics and comparing to historical team-level metrics. Uses validated feature selection, regularized regression, and cross-validation, with results compared against DraftKings Sportsbook win totals to assess accuracy.

## Objective
Predict team-level win totals in a way that is:
- Interpretable
- Data-driven
- Comparable to real-world market expectations

---

## Results

[Full model inputs and outputs (Google Sheet)](https://docs.google.com/spreadsheets/d/1Bn2G2w-NLKm78kQ27LpkRBgz-FAbYPT30Vjd82gPc_U/edit?gid=1174515623)

---

## Data Inputs

### 2023-2025 Historical Team-Level Metrics
- FanGraphs Team Batting and Pitching Stats

### 2026 Player Projections
- BAT X used for batting projections
- ATC used for pitching projections

These sources were selected based on the latest research available: [Most Accurate Fantasy Baseball Projections](https://www.fantasypros.com/2025/02/most-accurate-fantasy-baseball-projections-2024-results/). Player projections from these sources are aggregated into team-level projections.

---

## Feature Selection
Metrics were evaluated based on their historical relationship to team wins. The following team-level metrics were chosen as model inputs based on their historical correlation to team win totals.

- WAR: +0.91
- WHIP: −0.86
- ERA: −0.84
- OBP: +0.84
- Runs: +0.82
- K-BB%: +0.82
- SLG: +0.66

---

## Model Results
A regression-based model was used to translate team-level metrics into projected win totals.

Model performance was evaluated using cross-validation on unseen data to ensure the results were not driven by overfitting.

**Validation metrics:**
- **Mean Absolute Error (MAE):** ~2.5 wins  
- **Root Mean Squared Error (RMSE):** ~3.4 wins  
- **R²:** ~0.89  

These results indicate strong predictive power and low average error for team win total forecasting. Errors appear small for a 162 game season.

---

## Market Comparison
Model team win total projections were compared to DraftKings Sportsbook win total over/unders to further validate model accuracy. An r2 of .9182 was achieved when comparing the two. This comparison demonstrates that the model is well-calibrated while still providing independent output.

---

## Key Takeaways and Potential Improvements
- Team-level wins can be predicted effectively using a small number of carefully selected metrics. There is perhaps even some redundancy in the metrics selected that could be further refined.
- For a production-level projection it may be beneficial to use more than three years of historical data.
- Data quality and feature selection are of the utmost improtance.
- Benchmarking against proven markets is a valuable validation tool.

---

## Tools Used
- Python
- pandas
- scikit-learn
- matplotlib

---

## Author
Steve Myette

This project demonstrates applied analytics focused on data aggregation, feature selection, forecasting, and validation.
