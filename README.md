# **DSA210 PROJECT**

## **Project: Hormonal Cycle and Spending Habits**

## **Overview**

This project aims to analyze how hormonal cycle phases influence personal spending habits. By categorizing weekly expenditures and correlating them with different phases of the hormonal cycle, the project will uncover potential patterns and trends in financial behavior.

## **Motivation**

There is a common perception that women's financial behaviors are unpredictable due to hormonal fluctuations throughout their cycle. However, this assumption lacks empirical validation. This project seeks to challenge this notion by analyzing whether spending habits follow a **predictable pattern** in relation to hormonal phases. By systematically examining expenditure trends across different cycle phases, I aim to determine whether financial decisions are influenced by biological rhythms in a structured and measurable way.

**The findings of this study could contribute to:**

- **Personal Finance Strategies:** Understanding how biological cycles may affect budgeting.
- **Behavioral Economics:** Exploring the relationship between hormonal cycles and financial decision-making.

## **Data Sources**

- **Personal Spending Data:** Extracted from bank transaction records, categorized into:
  - Food
  - Personal care
  - Entertainment
  - Utilities
  - Health-related expenses
  - Miscellaneous purchases

- **Hormonal Cycle Tracking Data:** Extracted from Apple Health, including:
  - Follicular Phase
  - Ovulatory Phase
  - Luteal Phase
  - Menstrual Phase  
  Tracked using a period tracking app or manual records.

## **Methodology**

### 1. Data Extraction & Cleaning
- Categorized raw bank transaction records.
- Aligned weekly spending data with the corresponding hormonal phase.
- Ensured completeness and consistency across tracking period.

### 2. Exploratory Data Analysis (EDA)
- Descriptive statistics and visualizations of spending patterns across phases:
  - Category frequency distributions
  - Amount range histograms
  - Weekly trends for specific categories (e.g., dessert)

### 3. Correlation & Statistical Analysis
- Applied hypothesis tests:
  - T-Test, ANOVA, Mann-Whitney U for between-phase comparisons
- Used Pearson correlation to evaluate relationships between day-of-cycle and spending.

### 4. Insights & Interpretation
- Identified behavioral variations by phase.
- Discussed practical takeaways for budgeting strategies and self-awareness.

### 5. Predictive Modeling 

#### Task 1: Regression – Predict Daily Spending
- **Goal:** Estimate total daily spending using phase-related features.
- **Features:** Phase, day of cycle, category frequency, weekday/weekend
- **Models:** Linear Regression, Random Forest Regressor
- **Metrics:** RMSE, MAE, R²

#### Task 2: Classification – Predict Hormonal Phase
- **Goal:** Predict the hormonal phase using daily spending behavior.
- **Features:** Spending categories, total amount, purchase count, weekday
- **Models:** Logistic Regression, Random Forest Classifier
- **Metrics:** Accuracy, F1-score, Confusion Matrix

## **Data Collection Plan**

- Manual or automated recording of personal spending.
- Hormonal phase data tracked via period app or manually labeled.
- Data collected over multiple cycles to ensure balanced representation.

## **Expected Outcomes**

- Identification of cycle-sensitive spending categories.
- Discovery of measurable phase-behavior links.
- Practical applications for cycle-aware personal finance tools.

## **Visualizations**

- Category frequency bar charts
- Amount range histograms
- Weekly dessert spending time series
- Actual vs. predicted scatter plots
- Confusion matrices for classification results

## **Limitations**

- Single-person dataset limits generalizability.
- Potential inaccuracies in manually tracked phase data.
- Confounding variables (e.g., external life events) not controlled.
- Phase representation imbalance (e.g., fewer ovulation days).

## **Future Work**

- Expand to a multi-user dataset.
- Incorporate mood, sleep, biological markers for richer insights.
- Apply sequence-aware models (e.g., LSTM) for time-series prediction.
- Develop personalized, adaptive budgeting apps informed by cycle data.

## **Project Timeline**

| Date         | Milestone                               |
|--------------|------------------------------------------|
| March 10     | Project proposal (README + data plan)    |
| March 11–25  | Data collection and preliminary cleaning |
| March 26–Apr 10 | EDA and hypothesis testing           |
| Apr 11–25    | Visualizations and interpretation        |
| May 23       | Supervised learning implementation     |
| May 30       | Final report and GitHub completion       |

## **Files**

- `merged_dataset.csv` – Final enriched dataset
- `eda_analysis.ipynb` – Exploratory data analysis and visualizations
- `ml_regression_profit.py` – Regression model code
- `ml_phase_classifier.py` – Classification model code
- `requirements.txt` – Python package dependencies
- `README.md` – Project documentation


