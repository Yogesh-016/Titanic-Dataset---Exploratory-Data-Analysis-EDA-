# Titanic Dataset – Exploratory Data Analysis (EDA)

Exploratory Data Analysis on the classic Titanic dataset to understand passenger demographics, survival patterns, and feature relationships using statistics and visualizations.

## Objective

Understand the structure and story hidden in the Titanic dataset through:
- Summary statistics
- Distribution analysis (histograms, boxplots)
- Correlation and feature relationships
- Pattern, trend, and anomaly detection
- Data-driven inferences to guide future feature engineering / modeling

## Dataset

- **Source:** Titanic-Dataset.csv (891 rows, 12 columns)
- **Target variable:** `Survived` (0 = No, 1 = Yes)
- **Features:** `PassengerId`, `Pclass`, `Name`, `Sex`, `Age`, `SibSp`, `Parch`, `Ticket`, `Fare`, `Cabin`, `Embarked`

## Tools & Libraries

| Library | Purpose |
|---|---|
| Pandas | Data loading, summary statistics |
| Matplotlib | Static plotting |
| Seaborn | Statistical visualizations (histograms, boxplots, heatmaps, pairplots) |
| Plotly | Interactive visualization (Age vs Survival) |

## Project Structure

```
titanic-eda/
├── titanic_eda.py          # Main EDA script
├── Titanic-Dataset.csv      # Dataset (place in same directory)
└── README.md
```

## How to Run

1. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly
   ```
2. Place `Titanic-Dataset.csv` in the same folder as `titanic_eda.py`.
3. Run the script:
   ```bash
   python titanic_eda.py
   ```
   - Static charts (Matplotlib/Seaborn) will pop up in separate windows.
   - The interactive Plotly chart opens in your default browser.
   - For inline rendering, run the script cell-by-cell in a Jupyter Notebook / VS Code interactive window instead.

## Analysis Steps

1. **Summary Statistics** – mean, median, std, skew, and missing-value counts for numeric features; value counts for categorical features.
2. **Histograms & Boxplots** – distribution shape and outlier detection for `Age`, `Fare`, `SibSp`, `Parch`.
3. **Correlation Matrix & Pairplot** – relationships between numeric features and `Survived`.
4. **Pattern & Anomaly Detection** – IQR-based outlier detection, engineered `FamilySize` feature, interactive Age-vs-Survival distribution.
5. **Feature-Level Inferences** – written takeaways connecting each observation back to survival outcome.

## Key Findings

- **Sex is the strongest single predictor** – females survived at ~74% vs ~19% for males.
- **Class matters** – 1st class survival (~63%) nearly triples 3rd class survival (~24%).
- **Fare is heavily right-skewed** (skew ≈ 4.8), with high-fare outliers tied to 1st class / luxury cabins.
- **Age has ~20% missing values** and **Cabin has ~77% missing values** – both need handling before modeling (imputation, or a `HasCabin` binary flag for Cabin).
- **Moderate family size (2–4)** had a higher survival rate than solo travelers or large families (5+).
- **Pclass (−0.34) and Fare (+0.26)** show the strongest linear correlation with `Survived` among numeric features.

## Next Steps

- Handle missing values (`Age` imputation, `Cabin` → binary flag or drop)
- Encode categorical variables (`Sex`, `Embarked`)
- Feature engineering (`FamilySize`, `Title` extraction from `Name`, `HasCabin`)
- Baseline classification models (Logistic Regression, Random Forest) for survival prediction

## Author

**Yogesh S**
Final-year B.Tech, AI & Data Science, Dhanalakshmi College of Engineering (Anna University)
GitHub: [Yogesh-016](https://github.com/Yogesh-016)
LinkedIn: [yogesh-s-617334378](https://linkedin.com/in/yogesh-s-617334378)
