# FraudDetection
A Machine Learning project focused on detecting fraudulent transactions. It includes data preprocessing, exploratory data analysis (EDA), feature engineering, model building, and evaluation.
# Fraud Detection Project 🔍💳

This project focuses on detecting fraudulent transactions using machine learning techniques. It demonstrates how to handle imbalanced datasets, perform exploratory data analysis (EDA), build predictive models, and evaluate performance effectively.

## 📚 Project Overview
- **Objective**: Predict whether a transaction is fraudulent or not.
- **Tech Stack**: Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn.
- **Key Tasks**:
  - Data Cleaning & Preprocessing
  - Exploratory Data Analysis (EDA)
  - Feature Engineering
  - Model Building (e.g., Logistic Regression, Random Forest, XGBoost)
  - Model Evaluation (Confusion Matrix, Precision-Recall, ROC-AUC)

## 🚀 How to Run
1. Clone the repository:
2. Install the required libraries:
3. Open the notebook file (`fraud_detection.ipynb`) in Jupyter Notebook or any IDE like VS Code.

4. Run the cells step-by-step.

## 📈 Key Results
- Built models with high precision and recall to identify fraud cases.
- Applied oversampling/undersampling techniques to handle class imbalance.
- ROC-AUC score of **XX%** achieved with [your best model].

## 📋 Dataset
*(Mention source here)*  
Example: [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

## 🛠️ Libraries Used
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn (optional for oversampling/undersampling)

## ⚙️ Techniques Applied
- SMOTE (Synthetic Minority Over-sampling Technique)
- Cross-validation
- Hyperparameter tuning
- Feature scaling

## 📬 Contact
For any queries, feel free to reach out at [your-email@example.com].


1. Data Cleaning: Handling Missing Values, Outliers, and Multi-Collinearity
Missing Values:
The balance-related columns (oldbalanceOrg, newbalanceOrig, oldbalanceDest, newbalanceDest) contained missing values, particularly for accounts labeled as "Merchants." To address this, we imputed missing values with zeros, a reasonable assumption, as some accounts (such as new recipients) may lack prior balance data.
Outliers:
Outliers were detected in the amount column, especially in TRANSFER and CASH-OUT transaction types. Transactions exceeding a predefined threshold (e.g., >200,000) were flagged for potential fraud, as unusually large transactions can be strong fraud indicators.
Multi-Collinearity:
To mitigate multi-collinearity, we analyzed correlation matrices between balance columns and removed highly correlated features, such as oldbalanceOrg and newbalanceOrig. This step was essential to prevent redundant information that could negatively impact model performance.

2. Fraud Detection Model Overview
Multiple machine learning models were trained and evaluated to identify the most effective approach for fraud detection. These models include:
Logistic Regression: A baseline linear classification model.
Support Vector Machine (SVM): A non-linear classifier designed to optimize the boundary between fraudulent and non-fraudulent transactions.
Decision Tree: A simple tree-based model that splits data based on key features.
Random Forest: An ensemble method that aggregates multiple decision trees to improve accuracy.
XGBoost: A high-performance gradient boosting model.
Models were trained on 70% of the dataset and validated on the remaining 30%. Cross-validation was employed to prevent overfitting.

3. Feature Selection
Key features included in the model were:
Step: The hour of the transaction.
Type: The type of transaction (e.g., CASH-IN, CASH-OUT, TRANSFER).
Amount: Transaction value, a crucial factor in detecting fraud.
Old Balance Origin & New Balance Origin: Balance changes in the originating account.
Old Balance Destination & New Balance Destination: Shifts in the destination account balance.
Columns like nameOrig and nameDest, which serve only as identifiers, were excluded as they do not contribute to the detection of fraud.

4. Model Performance Metrics
Model	Accuracy	AUC-ROC	Precision	Recall	F1-Score
Logistic Regression	0.98	0.75	0.60	0.65	0.62
SVM	0.98	0.76	0.62	0.68	0.64
Decision Tree	0.99	0.88	0.81	0.79	0.80
Random Forest	0.99	0.92	0.84	0.83	0.83
XGBoost	0.99	0.94	0.88	0.85	0.86
Best Model: XGBoost outperformed other models across all key metrics, achieving an AUC-ROC of 0.94 and an F1-Score of 0.86. Given its superior precision and recall, it was deemed the most effective model for this task.

5. Key Fraud Predictors
The key variables driving fraud detection were:
Transaction Type: TRANSFER and CASH-OUT transactions are highly correlated with fraudulent activity.
Amount: Large transaction amounts, especially those exceeding a certain threshold, are common fraud indicators.
Balance Changes: Significant reductions in the originating account balance, particularly when funds are quickly transferred or withdrawn, are red flags.
Merchant Accounts: Unusual balance changes in accounts starting with "M" (merchant accounts) can suggest fraudulent behavior.

6. Validity of Predictors
These factors align with known fraud patterns:
High Transaction Values: Fraudsters often attempt to transfer large sums in a short period, aiming to deplete accounts before detection.
Targeted Transaction Types: Fraudulent activity is frequently concentrated in TRANSFER and CASH-OUT transactions, especially when significant funds are moved and rapidly withdrawn.
Rapid Balance Changes: Drastic shifts in account balances, particularly when unexpected, are telltale signs of fraud.

7. Recommended Fraud Prevention Measures
To safeguard the company’s infrastructure during updates, the following measures should be implemented:
Real-Time Fraud Detection: Integrate real-time monitoring to immediately flag suspicious high-value transactions.
Transaction Limits: Establish transaction limits for TRANSFER and CASH-OUT transactions, with multi-factor authentication required for any transaction exceeding the limit.
Behavioral Profiling: Use historical data to develop customer profiles based on typical transaction patterns. Deviations from expected behavior should trigger verification protocols.
Activity Alerts: Notify both the customer and internal security team when unusual activities are detected, enabling swift action.
Continuous Model Updates: Regularly update and retrain the fraud detection model to account for evolving fraud tactics.

8. Assessing the Effectiveness of Prevention Measures
To ensure these measures are effective, the following evaluation strategies are recommended:
Fraud Rate Comparison: Measure the incidence of flagged fraud before and after the implementation of new systems. A reduction would indicate success.
Performance Monitoring: Track performance metrics such as precision, recall, and false positive/negative rates. A higher precision without a corresponding drop in recall would signify improved detection accuracy.
A/B Testing: Apply the new measures to a sample group and leave the rest unchanged. A decrease in fraudulent activity within the test group would confirm the effectiveness of the measures.
Customer Feedback: Monitor customer complaints about unauthorized transactions. A reduction in complaints would reflect improved fraud detection.
Cost Analysis: Quantify financial savings resulting from reduced fraud incidents, which would demonstrate the impact of quicker detection.
By monitoring these key indicators, the company can continuously refine its fraud detection capabilities and safeguard its financial systems.


---
*Made❤ by Swati Singh* 
