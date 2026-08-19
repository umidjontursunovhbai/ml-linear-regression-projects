# 04 — Advanced House Prices

Bu dataset 01/02/03 dan qiyinroq: regression practice uchun synthetic, lekin real-life muammolarga o'xshash qilib yaratilgan.

## Target

Predict:

```text
price_usd
```

## Nega qiyinroq?

- numeric + categorical columns bor
- missing values bor
- duplicate rows bor
- outliers bor
- correlated features bor
- some effects non-linear: `age`, `area_m2`, `floor`, neighborhood interactions
- feature engineering qilsang performance yaxshilanishi mumkin

## Practice checklist

1. Load dataset
2. `head`, `shape`, `info`, `describe`
3. Missing values check
4. Duplicates check
5. Target distribution: `price_usd`
6. Outlier analysis
7. Categorical encoding: `pd.get_dummies()` / one-hot
8. Feature engineering:
   - `building_age = 2026 - build_year`
   - `floor_ratio = floor / total_floors`
   - maybe `is_luxury_area`, `price_per_m2` only for analysis, NOT as feature for predicting price
9. Train/test split
10. Baseline Linear Regression
11. Evaluate with MAE, RMSE, R²
12. Improve:
   - handle missing values better
   - remove/clip extreme outliers
   - add engineered features
   - compare models: LinearRegression, Ridge, RandomForestRegressor
13. Feature importance / coefficients
14. Write final conclusion

## Important warning

Do not use `property_id` as a feature.
Do not use `price_per_m2` as a feature if you calculate it from `price_usd`, because it leaks the answer.
