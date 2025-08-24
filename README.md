# -Maintenance-Cost-Minimization-of-Wind-Energy-Machinery-using-Machine-Learning
This project applies machine learning to predictive maintenance of wind turbines. Using sensor data (V1–V40), a tuned XGBoost model was developed to predict failures, achieving 99% accuracy. The model significantly reduces maintenance costs by optimizing repair vs. replacement decisions.
📌 Project Overview

This project applies Machine Learning (ML) to minimize the maintenance cost of wind energy production machinery by predicting failures before they occur.
The solution implements predictive maintenance using sensor data and turbine component attributes, enabling timely repairs and reducing costly replacements or unnecessary inspections.

🎯 Objectives

Predict machinery failure patterns in wind turbines (gearbox, blades, sensors, etc.).

Optimize maintenance scheduling to reduce operational costs.

Develop a custom cost-sensitive evaluation metric instead of only accuracy.

Build an end-to-end ML pipeline for productionization.

📂 Dataset

Two datasets were used:

Train Dataset (train.csv) → 40,000 rows

Test Dataset (test.csv) → 10,000 rows

Features:

V1–V40 → Sensor & machinery attributes (temperature, humidity, wind speed, gearbox, blades, etc.).

Target → Failure status (0 = No Failure, 1 = Failure).

Class Distribution (Imbalance):

No Failure (0) → 94.53% (37,813 samples)

Failure (1) → 5.47% (2,187 samples)

🔧 Data Preprocessing

Missing Values → Median imputation (V1, V2 had missing values).

Outlier Detection → Boxplot analysis showed positive & negative outliers across V4–V36.

Class Imbalance Handling →

SMOTE (Synthetic Oversampling)

Random Undersampling

No Data Leakage → Imputation & balancing applied separately to training and validation sets.

📐 Customized Cost Metric

Maintenance cost was modeled as:

Maintenance Cost
=
(
𝑇
𝑃
×
15
𝐾
)
+
(
𝐹
𝑁
×
40
𝐾
)
+
(
𝐹
𝑃
×
5
𝐾
)
Maintenance Cost=(TP×15K)+(FN×40K)+(FP×5K)

A custom metric was created:

Minimum_Vs_Model_Cost
=
(
𝑇
𝑃
+
𝐹
𝑁
)
×
15
𝑇
𝑃
×
15
+
𝐹
𝑃
×
5
+
𝐹
𝑁
×
40
Minimum_Vs_Model_Cost=
TP×15+FP×5+FN×40
(TP+FN)×15
	​


Repair Cost (Correct prediction) → $15K

Replacement Cost (Missed failure) → $40K

Inspection Cost (False alarm) → $5K

Higher score = Lower maintenance cost relative to minimum possible.

🤖 Models Built

Seven ML models were trained & validated with 5-Fold Cross Validation:

Logistic Regression

Decision Tree

Random Forest

Bagging Classifier

Boosting → AdaBoost, Gradient Boost, XGBoost

⚡ Model Performance

Final Model → Tuned XGBoost (RandomizedSearchCV)

Accuracy: 0.99 (99%)

Precision: >0.95

Recall: ~0.85

F1 Score: ~0.90

False Negatives (FN): 0.82%

False Positives (FP): 0.21%

Validation Cost Metric: 0.821

Test Cost Metric: 0.792

✅ This indicates the model generalizes well with very few misclassifications.

📊 Key Results
🔹 Feature Importance (Top Predictors)

V18

V39

V26

V3

V10

🔹 Cost Savings

Without ML Model → Maintenance costs ≈ 2.67 × minimum possible cost

With Tuned XGBoost Model → Maintenance costs ≈ 1.26 × minimum possible cost

Impact → Significant cost reduction advantage with predictive maintenance.

🚀 ML Pipeline & Deployment

An automated ML pipeline was built using Scikit-learn to:

Preprocess data (missing values, scaling, class balancing).

Train & validate models with cross-validation.

Tune hyperparameters using RandomizedSearchCV.

Save the final XGBoost model for deployment.

This ensures the solution is reproducible, production-ready, and scalable.

🏆 Business Insights

Predictive maintenance with ML reduces downtime, replacement costs, and inspection overheads.

The most important features (V18, V39, V26, V3, V10) should be prioritized for frequent monitoring.

Implementing the model in production provides large cost savings compared to traditional maintenance.
