# nba-feature-engineering-project
# Feature Engineering Notes

## 🎯 Target Variable
- **`target_5yrs`** is the dependent variable, representing whether a player remains in the NBA for at least 5 years.

## 🗑️ Dropped Columns
- **`name`**: Player identifiers are non-predictive and risk data leakage.

## 🔍 Correlation Analysis
- Generated a correlation heatmap to identify multicollinearity.
- Features with correlation > 0.85 were flagged for removal or careful monitoring.
- Example: `fgm` and `fga` are highly correlated with `fg` (field goal percentage), so we retain `fg` as the more interpretable metric.

## 🛠️ Engineered Features
- **Points Per Minute (PPM):** `pts / min`  
  Captures scoring efficiency relative to playing time.
- **Efficiency Rating:** `(fg + ft) + (reb + ast) - tov`  
  Simplified composite metric balancing shooting accuracy, rebounding, playmaking, and turnover control.

## 🧹 Handling Missing Values
- Checked all numeric columns for nulls.
- Imputed missing values using **column means** to preserve dataset size and avoid introducing bias.

## ✅ Final Dataset
- Cleaned, reduced, and enriched with composite features.
- Saved as `data/processed/nba_cleaned.csv`.

---

### 📌 Key Justifications
- **Transparency:** Every drop or addition is documented for reproducibility.
- **Interpretability:** Composite features are intuitive and directly tied to player performance.
- **Fairness:** Mean imputation avoids skewing results toward extremes.
