# DSA210 PROJECT

## Project: Hormonal Cycle and Spending Habits

---

## Overview

This project investigates how hormonal cycle phases may influence daily personal spending behavior. By categorizing financial transactions and aligning them with menstrual phases, the project identifies patterns between biological rhythms and economic decisions.

---

## Motivation

There is a common assumption that women's spending behaviors are unpredictable due to hormonal fluctuations. This project challenges that assumption by evaluating whether spending follows structured, phase-dependent patterns using data analysis and predictive modeling.

**This study contributes to:**
- **Personal Finance Strategies:** Creating cycle-aware budgeting insights.
- **Behavioral Economics:** Exploring phase-based decision-making shifts.

---

## Data Sources

- **Spending Data:** Daily categorized expenses from personal bank records, including:
  - Food, personal care, entertainment, subscriptions, health, etc.
- **Hormonal Cycle Data:** Tracked via Apple Health and labeled by:
  - Menstrual, Follicular, Ovulatory, and Luteal phases

---

## Methodology

### 1. Data Processing
- Grouped transaction data by day and spending category.
- Merged with phase data using date.
- Added features: weekday, weekend, total_spent, and log-transformed spending.

### 2. Exploratory Data Analysis (EDA)
- Visualized category frequency and amount distributions.
- Compared spending trends across phases.
- Used histograms, bar plots, and time series (e.g., dessert category).

#### Spending Frequency by Category
![Unknown-2](https://github.com/user-attachments/assets/09dfa492-4e56-492a-8899-b01391a6d1bd)

*Most expenditures occur in categories like food, coffee, and subscriptions, indicating frequent daily spending in essential and lifestyle items.*

#### Spending Amount Distribution
![Unknown-3](https://github.com/user-attachments/assets/0bde282a-cdd0-49e9-aad4-4a523f1947d5)

*Most transactions fall within smaller amount ranges, consistent with typical daily expenses.*

#### Weekly Dessert Spending Trend
![Unknown-4](https://github.com/user-attachments/assets/3425192a-90bc-47ba-9b10-af4bb20acef7)

*Weekly dessert spending varies over time but shows no strong cyclical pattern aligned with hormonal phases.*

#### Count of Period vs. Non-Period Days
![Unknown-6](https://github.com/user-attachments/assets/a3163979-17c6-40ae-bd83-433d84f3f3c6)
 
*The dataset contains a balanced number of menstruation and non-menstruation days, allowing meaningful phase comparisons.*

#### Average Spending by Menstrual Phase
![Unknown-11](https://github.com/user-attachments/assets/e284dc1e-6b32-48dc-b0de-f3e138a9ee2e)

*Average spending shows minor variations across phases, with no phase strongly dominating total expenditure.*

#### Spending Intensity Heatmap by Day and Month
![Unknown-10](https://github.com/user-attachments/assets/4208acbe-5965-4149-ba94-f76cdabf1fbe)

*Spending intensity varies by day and month, indicating periods of higher and lower activity not obviously linked to menstrual phases.*

#### Correlation Among Weekly Spending Categories
![heatmap](https://github.com/user-attachments/assets/73e8da70-cd26-4e73-981b-e95b4cba1931)

*Certain spending categories like money transfer & other, coffee & cosmetics show moderate to strong positive correlation, suggesting linked spending behaviors.*

#### Emotional Spending Distribution by Phase
![violin](https://github.com/user-attachments/assets/b9804357-88a3-4c49-943e-8a89a849f1e5)

*Emotional spending categories such as dessert, cosmetics, coffee, and food exhibit similar distributions across phases, with no significant shifts.*


### 3. Statistical Analysis
- Applied T-Test, ANOVA, Mann–Whitney U, Fisher’s Exact Test, and Permutation Tests to compare phase-based spending.
- Used Pearson correlation to explore relationships with cycle days.
  ## Hypotheses and Statistical Testing

In this project, several hypotheses were tested to examine how hormonal cycle phases affect spending behavior. Below are the key hypotheses, the tests performed, and the insights derived from the results.

---

# Hypothesis Testing Results and Visualizations

### Hypothesis 1: Dessert Spending during Luteal Phase (Permutation Test)  
- **Null Hypothesis (H₀):** The mean dessert spending during the Luteal phase is less than or equal to that during other phases.  
- **Alternative Hypothesis (H₁):** The mean dessert spending during the Luteal phase is greater than that during other phases.  
- **Test:** Permutation Test (outlier-filtered)  
- **Result:**  
  - p-value = 0.4424 — **Fail to reject H₀**  
- **Insight:** Dessert spending is not significantly higher in the Luteal phase.

![hyp1](https://github.com/user-attachments/assets/497a253f-b4b2-433b-930e-f905ee9d51f4)


---

### Hypothesis 1.1: Dessert Spending during Luteal Phase (Mann–Whitney U Test)  
- **Test:** Mann–Whitney U Test (full dataset)  
- **Result:**  
  - p-value = 0.4444 — **Fail to reject H₀**  
- **Insight:** Confirming no significant difference in dessert spending by phase.

![hyp2](https://github.com/user-attachments/assets/0758a903-cf71-44dc-acca-278002601e21)


---

### Hypothesis 2: Cosmetics Spending during Luteal Phase  
- **Test:** Permutation Test (one-tailed)  
- **Result:**  
  - p-value = 0.3719 — **Fail to reject H₀**  
- **Insight:** Cosmetics spending does not significantly vary with hormonal phases.

![hyp3](https://github.com/user-attachments/assets/5047cb5f-bfe3-461c-9f37-13eb18b52285)


---

### Hypothesis 3: Clothing Spending during Ovulation Phase  
- **Test:** Mann–Whitney U Test (one-tailed)  
- **Result:**  
  - p-value = 0.5556 — **Fail to reject H₀**  
- **Insight:** Ovulation phase does not significantly increase clothing spending.

![hyp4](https://github.com/user-attachments/assets/9b92a981-ef06-4798-912b-23419a26bd9e)


---

### Hypothesis 4: Weekly Total Spending during Luteal Phase  
- **Test:** Welch’s t-test (one-tailed)  
- **Result:**  
  - p-value = 0.7453 — **Fail to reject H₀**  
- **Insight:** Weekly total spending is not significantly higher during the Luteal phase.

![hyp5](https://github.com/user-attachments/assets/91402208-99db-438e-88ef-7e40aeb80611)


---

### Hypothesis 5: Proportion of Coffee Purchases on Period Days  
- **Test:** Fisher’s Exact Test  
- **Result:**  
  - p-value = 0.0283 — **Reject H₀**  
- **Insight:** Coffee purchases occur significantly more frequently during menstruation.

![hyp 6](https://github.com/user-attachments/assets/304e278a-b1af-4cc6-adfd-722d8fa92b6f)


---

## Summary  
Except for coffee purchase frequency, no other spending categories show statistically significant differences associated with menstrual cycle phases in this dataset.

### 4. Predictive Modeling

#### Task 1: Regression – Predict Daily Spending
- **Model:** Random Forest Regressor
- **Features:** 14 spending category columns + weekday/weekend
- **Target:** `log_total_spent`
- **Metrics:** MAE, RMSE, R², 5-fold Cross-validation
- **Visuals:**
  - Scatter plot (Actual vs. Predicted)
  - Residual histogram
  - Boxplot of spending by phase

#### Task 2: Classification – Predict Hormonal Phase
- **Model:** Random Forest Classifier
- **Features:** Same as regression + `total_spent`
- **Target:** `phase`
- **Metrics:** Accuracy, F1-score, confusion matrix
- **Visuals:**
  - Confusion matrix
  - Phase-specific accuracy bar chart
  - Feature importance rankings

---

## Machine Learning Key Results

### Task 1 – Regression: Predicting Daily Spending

- **Model:** Random Forest Regressor  
- **Performance Metrics:**  
  - **Test R²:** 0.8927 — approximately 89.3% of variance in log-transformed total daily spending explained, reflecting strong predictive power.  
  - **Cross-validated R²:** 0.708 — consistent performance across data splits, confirming robustness.  
  - **Mean Absolute Error (MAE):** 0.36 — average deviation of predicted log spending from actual values, indicating reasonable accuracy.  
  - **Root Mean Squared Error (RMSE):** 0.56 — shows model’s ability to limit large prediction errors.  
- **Visualizations:**  
  - Scatter plot of Actual vs. Predicted spending shows close alignment along the ideal line.  ![Unknown-29](https://github.com/user-attachments/assets/ce95bc3d-cf09-43c2-9c70-da7c8c3fc949)

  - Residual histogram centered around zero with no bias.  ![Unknown-27](https://github.com/user-attachments/assets/cf5fa476-4a6b-4b6b-9a6a-933d480eaa20)

  - Model’s average predicted spending aligns closely with actual spending for all phases ![Unknown-28](https://github.com/user-attachments/assets/c2e9dcca-5593-4829-b0ba-4f878bc9ba59)

- **Insight:** The regression model captures complex, nonlinear relationships between spending categories and daily spending, enabling reliable forecasts.

---

### Task 2 – Classification: Predicting Hormonal Phase

- **Model:** Random Forest Classifier  
- **Performance Metrics:**  
  - **Accuracy:** 37.3% — modest, reflecting difficulty of predicting hormonal phase solely from spending patterns.  
  - **F1 Score:** 0.31 — limited balance between precision and recall, suggesting potential for improvement.  
- **Class Imbalance:** Better prediction accuracy for some phases (e.g., Luteal) due to uneven data distribution.  
- **Visualizations:**  
  - Confusion matrix reveals phase-specific misclassifications.  ![Unknown-24](https://github.com/user-attachments/assets/32a4feb7-17a5-438f-b66a-1516ac828942)

  - Feature importance highlights spending categories influential in phase prediction.  ![Unknown-25](https://github.com/user-attachments/assets/f84cc542-b6fe-43e8-b829-597ba293914c)

  - Phase-specific accuracy charts detail strengths and weaknesses per phase.
  ---![Unknown-22](https://github.com/user-attachments/assets/137eb791-1532-42b1-a20d-a95ca9c43ef2)
- **Insight:** Despite limited accuracy, the model identifies spending features linked to hormonal phases, motivating further work with richer data or advanced models.

---

## Limitations

- Single-user dataset: results are not generalizable.  
- Phase representation imbalance (e.g., few ovulation days).  
- No behavioral confounders (e.g., mood, stress, income events) included.

---

## Future Work

- Expand dataset to multiple users for general insights.  
- Include behavioral markers like mood, sleep, productivity.  
- Apply sequence-aware models (e.g., LSTM) to capture time dynamics.

