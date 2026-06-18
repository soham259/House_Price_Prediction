# 🏠 House Price Prediction

Internship Project — Week 1
**Author:** Bhadwe (Soham Tanaji Raut)

A regression project that predicts house prices from property features (area, bedrooms,
bathrooms, amenities, etc.) and identifies which features influence price the most.

## 📁 Project Structure

```
HousePricePrediction_Bhadwe/
├── analysis.ipynb        # Full notebook: all 5 tasks, code + outputs
├── Housing.csv            # Dataset (545 rows, 13 columns)
├── summary.docx           # 1-page written summary of findings
├── README.md              # This file
└── charts/
    ├── histogram.png           # Distribution of house prices
    ├── heatmap.png              # Correlation heatmap of all features
    ├── extra_plot.png           # Actual vs Predicted price scatter (Random Forest)
    └── feature_importance.png   # Bonus: top features by Random Forest importance
```

## 📦 Dataset

[Housing Prices Dataset](https://www.kaggle.com/datasets/yasserh/housing-prices-dataset) (Kaggle)
— 545 properties, 13 columns, no missing values, no duplicates.

**Target column:** `price`
**Feature columns:** `area`, `bedrooms`, `bathrooms`, `stories`, `mainroad`, `guestroom`,
`basement`, `hotwaterheating`, `airconditioning`, `parking`, `prefarea`, `furnishingstatus`

## 🛠 Tools & Libraries

- Python 3.x, Jupyter Notebook
- pandas, numpy — data loading & cleaning
- scikit-learn — Linear Regression, Random Forest, train/test split, metrics
- matplotlib, seaborn — visualization

## ▶️ How to Run

1. Install dependencies:
   ```
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```
2. Make sure `Housing.csv` is in the same folder as `analysis.ipynb`.
3. Launch and run all cells:
   ```
   jupyter notebook analysis.ipynb
   ```
   Charts will regenerate automatically into the `charts/` folder.

## ✅ What's Inside the Notebook

| Task | Contents |
|------|----------|
| 1. Data Loading & Exploration | Load CSV, first 10 rows, shape, target/feature identification, missing-value check |
| 2. Data Cleaning | Missing-value handling, duplicate removal, one-hot encoding of categorical columns |
| 3. Model Building | 80/20 split, Linear Regression, Random Forest, MAE/RMSE/R² evaluation, model comparison |
| 4. Visualization | Price histogram, correlation heatmap, actual-vs-predicted scatter, feature importance |
| 5. Insights & Summary | Auto-generated + written 5–8 line summary of findings |

## 📊 Key Results

| Model | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Linear Regression | 970,043 | 1,324,507 | **0.653** |
| Random Forest Regressor | 1,013,969 | 1,398,116 | 0.613 |

**Linear Regression performed slightly better** than Random Forest on this dataset — price
scales fairly linearly with area and amenities, and with only 545 rows there isn't enough data
for Random Forest's extra flexibility to pay off.

**Top 3 features driving price:** `area` (~47% importance) → `bathrooms` (~15%) →
`airconditioning`, `parking`, `stories` (smaller, roughly equal contributions).

## 💡 Business Takeaway

Price and market listings primarily around **area** plus a small set of high-impact amenities
(air conditioning, parking, preferred location). A simple linear model is a fast, low-maintenance
first-pass valuation tool to use ahead of a human appraiser's final review.

See `summary.docx` for the full write-up.
