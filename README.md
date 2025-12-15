# Diabetes Dataset - Exploratory Data Analysis (EDA) & Visualization

## 1. Overview
This project focuses on exploring the **Diabetes Dataset** to understand patterns, trends, and relationships among features and their relationship with diabetes diagnosis. The dataset contains 768 entries with 9 columns, including patient information such as Glucose, BMI, Age, Insulin, Blood Pressure, and Outcome (0 = Non-diabetic, 1 = Diabetic).

**Key Goals:**
- Perform exploratory data analysis (EDA)
- Visualize feature distributions and relationships
- Identify important predictors for diabetes
- Interpret insights for data-driven decision making

---

## 2. Libraries Used

## 3. Dataset Overview

Number of entries: 768

Columns: 9

Target: Outcome (0 = No Diabetes, 1 = Diabetes)

Column	Type	Description
Pregnancies	int64	Number of pregnancies
Glucose	int64	Plasma glucose concentration
BloodPressure	int64	Diastolic blood pressure
SkinThickness	int64	Triceps skinfold thickness
Insulin	int64	2-Hour serum insulin
BMI	float64	Body Mass Index
DiabetesPedigreeFunction	float64	Genetic diabetes risk function
Age	int64	Age of the patient
Outcome	int64	Diabetes outcome (0/1)

Initial Observations:

Glucose, BMI, and Age are normally distributed.

Insulin and SkinThickness have spikes at 0 → missing or imputed values.

Pregnancies is right-skewed.

BMI shows many overweight individuals (30–40 range).

## 4. Exploratory Data Analysis (EDA)
4.1 Univariate Analysis

Histograms/KDEs: Used to visualize the distribution of numeric features.

Observations:

Middle-aged adults are at higher risk of diabetes.

High BMI is a major contributing factor.

4.2 Correlation Analysis
corr = df.corr(numeric_only=True)
sns.heatmap(corr, annot=True, cmap='coolwarm', fmt=".2f", square=True)
plt.title("Correlation Matrix of Diabetes Features")
plt.show()


Key Insights:

Glucose has the strongest positive correlation with Outcome (0.47).

BMI, Age, and Pregnancies show moderate positive correlation.

Insulin, BloodPressure, SkinThickness have weak correlation.

4.3 Bivariate Analysis

Scatter Plots: Glucose vs BMI, Age vs BMI, Insulin vs Glucose.

Boxplots/Violin Plots: Age, BMI, Insulin vs Outcome.

Count Plots: Outcome distribution (65% non-diabetic, 35% diabetic).

Pairplots: Multi-feature relationship analysis by Outcome.

## 5. Age-Specific Insights

Blood Pressure median rises with age; older adults show higher variability.

Insulin levels show wide variation across age groups; zero values indicate missing data.

Diabetes prevalence increases sharply after age 40; highest in 50–69 age group.

Age is moderately positively correlated with diabetes outcome (≈0.24).

## 6. Key Feature Insights
Feature	Observation	Interpretation
Glucose	High correlation with diabetes	Critical predictor
BMI	Higher BMI in diabetic patients	Overweight/obesity risk factor
Age	Older age in diabetic patients	Risk increases with age
Pregnancies	Slight positive correlation	Could affect female diabetes risk
Insulin	Many zero values	Needs imputation or cleaning
## 7. Data Quality Notes

Zero values in Insulin and SkinThickness → imputation required.

Mild class imbalance (0:65%, 1:35%) → handle during modeling.

No significant multicollinearity → most features retained after scaling.

## 8. Practical Implications

High-risk groups: Middle-aged, high BMI, high Glucose.

Predictive modeling should focus on Glucose, BMI, Age.

Lifestyle interventions (diet, exercise) crucial for overweight/older populations.

## 9. Next Steps

Handle missing/zero values in Insulin and SkinThickness.

Address class imbalance (SMOTE, stratified sampling, or weighting).

Standardize/normalize features.

Build predictive models (Logistic Regression, Random Forest, XGBoost).

Use visualizations to interpret model predictions and feature importance.

## 10. Example Visualizations

Distribution plots (Histograms/KDE)

Correlation Heatmap

Scatterplots for feature relationships

Boxplots/Violin plots by Outcome

Pairplots for multi-feature exploration

Outcome count plots

