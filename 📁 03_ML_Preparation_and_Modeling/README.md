# 🤖 ML Preparation & Credit Risk Modeling

🔍 Objective
Convert clean data into machine-readable features, train a model, and generate credit risk predictions.

🔹 Step 1: Feature Engineering
-- What We Do

Convert categorical columns using StringIndexer
Combine numeric + categorical features
Create a single feature vector

-- Why This Is Needed

ML models cannot understand text or separate columns.

🔹 Step 2: Model Selection
Model Used

Logistic Regression

-- Why Logistic Regression?

Ideal for binary classification (risk / no risk)
Interpretable
Fast and scalable

Commonly used in financial risk modeling

🔹 Step 3: Model Training

Split data into train & test sets
Train model on historical data
Learn patterns associated with default risk

🔹 Step 4: Evaluation
-- Metric Used

AUC (Area Under ROC Curve)
Why AUC?
Measures ranking quality
Works well for imbalanced risk datasets

🔹 Step 5: Prediction Output

Each loan receives:
Risk probability
Final prediction (0 = Low Risk, 1 = High Risk)

📤 Final Output

Risk scores usable by:
Credit teams
Risk analysts
Business stakeholders

📌 Key Takeaway 
“Instead of guessing, we now assign a risk score to every loan.”
