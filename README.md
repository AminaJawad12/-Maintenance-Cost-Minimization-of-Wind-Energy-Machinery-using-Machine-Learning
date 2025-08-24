# Maintenance Cost Minimization of Wind Energy Machinery using Machine Learning

This project applies **machine learning** for **predictive maintenance of wind turbines**, using sensor and component data (V1–V40).  
A tuned **XGBoost model** was developed, achieving **99% accuracy**, and significantly reducing maintenance costs by optimizing **repair vs. replacement** decisions.

---

## 📌 Project Overview
- Predict failures in wind turbine machinery (gearbox, blades, sensors, etc.).
- Optimize maintenance scheduling to reduce costs.
- Use a **custom cost-sensitive metric** (repair $15K, replacement $40K, inspection $5K).
- Build an end-to-end **ML pipeline** for production.

---

## 📂 Dataset
- **Train dataset**: 40,000 rows  
- **Test dataset**: 10,000 rows  
- **Features**: V1–V40 (sensor & machinery attributes)  
- **Target**: Failure (1) / No Failure (0)  
- Imbalance: 94.5% no-failure vs. 5.5% failure  

---

## 🔧 Methods
- Median imputation for missing values.  
- Outlier detection with boxplots.  
- Class imbalance handled via **SMOTE & Random Undersampling**.  
- 5-Fold Cross Validation for model evaluation.  
- Hyperparameter tuning with **RandomizedSearchCV**.  

---

## ⚡ Model Results
- **Final Model**: XGBoost (tuned)  
- **Accuracy**: 0.99  
- **Precision**: >0.95  
- **Recall**: ~0.85  
- **F1 Score**: ~0.90  
- **Cost Metric**: 0.792 (test set)  

🔹 **Feature Importance (Top 5)**: V18, V39, V26, V3, V10  
🔹 **Cost Savings**:  
   - Without ML → ~2.67 × minimum cost  
   - With ML → ~1.26 × minimum cost  

---

## 🚀 Deployment
- Automated pipeline built with **Scikit-learn**.  
- Handles preprocessing, model training, hyperparameter tuning, and deployment.  
- Ready for integration into production systems.  

---

## 🏆 Business Impact
- Reduces turbine downtime and replacement costs.  
- Prioritizes critical sensors (V18, V39, V26, V3, V10).  
- Demonstrates **significant cost-saving advantage** for wind energy production.  

---

## 📄 License
This project is licensed under the MIT License.
