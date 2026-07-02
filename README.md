# House Price Prediction System

Machine learning project to predict house prices from property features.

## Objective

Predict house prices using regression models based on property attributes (area, bedrooms, bathrooms, amenities, etc.), and identify which features drive pricing the most.

## Dataset

- **File:** `Housing.csv`
- **Size:** 545 records, 13 features
- **Target:** `price`
- No missing values or duplicates found

## Workflow

1. **Data Loading & Exploration** — shape, types, null checks
2. **Data Cleaning** — encoded binary yes/no columns (`mainroad`, `guestroom`, `basement`, `hotwaterheating`, `airconditioning`, `prefarea`) as 1/0; one-hot encoded `furnishingstatus`
3. **Model Building** - 80/20 train-test split; trained and compared:
   - Linear Regression
   - Random Forest Regressor
4. **Evaluation** - MAE, RMSE, R² Score
5. **Visualization** - price distribution, correlation heatmap, actual vs. predicted price plot
6. **Insights & Business Recommendations**

## Results

| Model | MAE | RMSE | R² Score |
|---|---|---|---|
| **Linear Regression** | 970,043 | 1,324,507 | **0.6529** |
| Random Forest | 1,022,560 | 1,401,497 | 0.6114 |

**Linear Regression outperformed Random Forest** - a slightly counterintuitive result, since Random Forest is the more complex model. This suggests the underlying price relationships in this dataset are largely linear, and the added complexity of Random Forest didn't translate into better generalization on this data size.

## Key Findings

- **Area, number of bathrooms, and stories** are the strongest predictors of house price
- The Linear Regression model explains **65% of price variation** in the dataset
- Simpler models can outperform complex ones on smaller, linearly-structured datasets

## Business Recommendation

Real estate agents and valuers should prioritize **area** and **number of bathrooms** as key factors when pricing properties.

## Tech Stack

`Python` · `pandas` · `numpy` · `scikit-learn` · `matplotlib` · `seaborn`

## Repository Structure

```
├── analysis.ipynb          # Full analysis notebook
├── Housing.csv              # Dataset
├── summary.pdf              # Project summary
├── charts/                  # Generated visualizations
│   ├── Chart_1_price_distribution.png
│   ├── chart_2_correlation_heatmap.png
│   └── chart_3_actual_vs_predicted.png
└── README.md
```

---
*Part of an ongoing ML project series documenting my Data Science internship journey — follow along on [LinkedIn].*
