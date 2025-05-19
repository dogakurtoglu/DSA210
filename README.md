# **DSA210 PROJECT**

## **Project: Hormonal Cycle and Spending Habits**

---

## **Overview**

This project investigates how hormonal cycle phases may influence daily personal spending behavior. By categorizing financial transactions and aligning them with menstrual phases, the project identifies patterns between biological rhythms and economic decisions.

---

## **Motivation**

There is a common assumption that women's spending behaviors are unpredictable due to hormonal fluctuations. This project challenges that assumption by evaluating whether spending follows structured, phase-dependent patterns using data analysis and predictive modeling.

**This study contributes to:**
- **Personal Finance Strategies:** Creating cycle-aware budgeting insights.
- **Behavioral Economics:** Exploring phase-based decision-making shifts.

---

## **Data Sources**

- **Spending Data:** Daily categorized expenses from personal bank records, including:
  - Food, personal care, entertainment, subscriptions, health, etc.
- **Hormonal Cycle Data:** Tracked via Apple Health and labeled by:
  - Menstrual, Follicular, Ovulatory, and Luteal phases

---

## **Methodology**

### 1. Data Processing
- Grouped transaction data by day and spending category
- Merged with phase data using date
- Added features: weekday, weekend, total_spent, and log-transformed spending

### 2. Exploratory Data Analysis (EDA)
- Visualized category frequency and amount distributions
- Compared spending trends across phases
- Used histograms, bar plots, and time series (e.g., dessert category)

### 3. Statistical Analysis
- Applied T-Test, ANOVA, and Mann-Whitney U to compare phase-based distributions
- Used Pearson correlation to explore relationships with cycle days

### 4. Predictive Modeling

#### 🔷 Task 1: Regression – Predict Daily Spending
- **Model:** Random Forest Regressor
- **Features:** 14 category columns + weekday/weekend
- **Target:** `log_total_spent`
- **Metrics:** MAE, RMSE, R², 5-fold Cross-validation
- **Visuals:**
  - Scatter plot (Actual vs. Predicted)
  - Residual histogram
  - Boxplot of spending by phase

#### 🔷 Task 2: Classification – Predict Hormonal Phase
- **Model:** Random Forest Classifier
- **Features:** Same as regression + `total_spent`
- **Target:** `phase`
- **Metrics:** Accuracy, F1-score, confusion matrix
- **Visuals:**
  - Confusion matrix
  - Phase-specific accuracy bar chart
  - Feature importance rankings

---

## **Key Results**

### Task 1 – Regression:
- **Test R²:** 0.8927  
- **Cross-validated R²:** 0.708  
- **MAE:** 0.36, **RMSE:** 0.56  
✅ Model accurately predicts log spending based on daily behavior

### Task 2 – Classification:
- **Accuracy:** 0.373  
- **F1 Score:** 0.31  
⚠️ Model performs well only on certain phases (e.g., Luteal), limited by data imbalance

---

## **Limitations**
- Single-user dataset: results are not generalizable
- Phase representation imbalance (e.g., few ovulation days)
- No behavioral confounders (e.g., mood, stress, income events) included

---

## **Future Work**
- Expand dataset to multiple users for general insights
- Include behavioral markers like mood, sleep, productivity
- Apply sequence-aware models (e.g., LSTM) to capture time dynamics

---

## **Visualizations**
- Bar plots and histograms by spending category
- Time series for specific categories
- Boxplots by phase
- Scatter plots and residuals (regression)
- Confusion matrix and accuracy charts (classification)

---

## **Project Timeline**

| Date         | Milestone                               |
|--------------|------------------------------------------|
| March 10     | Project proposal (README + data plan)    |
| March 11–25  | Data collection and cleaning              |
| March 26–Apr 10 | EDA and statistical tests             |
| Apr 11–25    | Modeling and visualization               |
| May 23       | Supervised learning completed            |
| May 30       | Final report and submission              |

---

