# Early-Credit-Risk-Prediction-using-Machine-Learning

📌 Project Overview

This project demonstrates an end-to-end Machine Learning workflow to build an Early Credit Risk Prediction system using historical loan applicant data.
The goal is to identify risky loan applicants early, before loan approval, so that financial institutions can make better, data-driven decisions and reduce potential losses.

The project is designed to be:

Beginner-friendly
Explainable to non-technical stakeholders
Aligned with real-world banking use cases
Built using free tools and open datasets

🎯 Problem Definition & AI Framing
🔍 Business Problem

Financial institutions process thousands of loan applications daily.
Approving loans for high-risk applicants can lead to loan defaults, which directly impact business profitability.
Traditional rule-based systems (fixed income thresholds, rigid credit rules):
Fail to capture complex risk patterns
Do not adapt to changing borrower behavior
Produce binary decisions without confidence levels

🧠 Why AI is Needed

Machine Learning is used because:
Credit risk depends on multiple interacting factors
Risk patterns are not linear
ML models can produce probability-based risk scores, not just yes/no decisions

🎯 Objective

To build a Machine Learning system that:
Predicts whether a loan applicant is high risk or low risk
Provides a probability of default
Supports early decision-making before loan approval

🔢 ML Framing

Problem Type: Binary Classification

Inputs: Applicant & loan attributes

Output:

Risk Prediction (0 = Low Risk, 1 = High Risk)
Probability of Default

🗂️ End-to-End Project Architecture
Raw Loan Data
      ↓
Bronze Layer (Raw Storage)
      ↓
Silver Layer (Cleaned & Validated Data)
      ↓
ML Preparation (Feature Engineering)
      ↓
Model Training & Evaluation
      ↓
Risk Prediction & Probability Scores

This architecture follows modern data + AI best practices.

🥉 Bronze Layer – Raw Data Ingestion
🎯 Purpose

The Bronze layer stores the raw dataset exactly as received, without modifying its content.

Key Characteristics

No cleaning
No transformation
No ML logic

Why This Matters

Preserves original data for traceability
Enables reproducibility
Acts as a single source of truth

👉 Think of the Bronze layer as safe storage of facts.

🥈 Silver Layer – Data Cleaning & Validation
🎯 Purpose

Prepare reliable and realistic data for Machine Learning.

Key Actions

Handle missing values in critical columns
Remove invalid records (e.g., zero or negative income)
Ensure realistic loan amounts and interest rates
Standardize schema
Rename target column to label

Why This Matters

Machine Learning models are highly sensitive to bad data.
This step ensures the model learns from trustworthy information.

🤖 ML Preparation – Feature Engineering
🎯 Purpose

Convert business data into a machine-readable format.

Step-by-Step Breakdown

1️⃣ Handling Missing Values

Only rows with complete, meaningful information are retained.

2️⃣ Encoding Categorical Variables

Text-based fields such as:

Loan intent
Loan grade
Home ownership are converted into numeric values using StringIndexer.

3️⃣ Feature Assembly

All numerical and encoded categorical features are combined into a single vector using VectorAssembler.
Final ML Dataset Contains
features → Vector of all input features
label → Target variable (credit risk outcome)
This structure is required by Spark ML algorithms.

⚙️ Model Selection & Technical Reasoning
🤖 Model Used: Logistic Regression

Why Logistic Regression?

Industry-standard baseline for credit risk
Interpretable and transparent
Produces probability scores
Suitable for regulated financial environments
Limitations

May not capture highly complex non-linear patterns

Chosen intentionally for explainability and stability

🧪 Model Training Strategy

Dataset split into:
70% Training Data
30% Test Data
Ensures fair evaluation on unseen data
Prevents overfitting

📊 Model Evaluation & Metrics
Metric Used: AUC (Area Under ROC Curve)
Why AUC?

Measures how well the model separates high-risk vs low-risk applicants

Robust to class imbalance

Widely accepted in financial risk modeling

Interpretation

AUC = 0.5 → Random guessing
AUC = 1.0 → Perfect separation
Higher AUC → Better risk discrimination
The model achieved a strong AUC score, indicating effective risk separation.

📈 Model Outputs (Business-Focused)

For each loan applicant, the model produces:

| Output      | Description           |
| ----------- | --------------------- |
| Prediction  | High Risk / Low Risk  |
| Probability | Likelihood of default |
| Confidence  | Model certainty       |

Example (Non-Technical Explanation)
“This applicant has an 82% probability of default, so the model flags them as high risk.”


🧠 AI Innovation & Insight Generation (Most Important)

This project goes beyond just training a model.

Key Innovation

Instead of using only binary predictions, the system outputs probability-based risk scores.
Risk Segmentation (Conceptual)
Low Risk → Probability < 0.3
Medium Risk → 0.3 – 0.6
High Risk → > 0.6

Why This Matters

Enables proactive risk management
Supports tiered decision-making
Converts ML output into actionable insights

This transforms predictions into business decisions, not just numbers.

🗄️ Database ↔ AI Workflow

Data loaded from Delta tables
Cleaned and validated through structured layers
Features extracted directly from database
ML consumes table-based data
Predictions generated from database-driven pipeline

This ensures:

Reproducibility
Traceability
Clean AI workflow integration

💼 Business Impact & Practical Use

This system can help:
Reduce loan defaults
Improve credit decision quality
Enable early risk detection
Support data-driven lending strategies

📌 Key Takeaways

End-to-end AI pipeline implemented
Clear separation of data layers
Explainable ML model
Business-focused decision support
Beginner-friendly and interview-ready

🚀 Future Enhancements

Advanced models (Random Forest, XGBoost)
Hyperparameter tuning
Fairness & bias analysis
Automated retraining
Deployment as a scoring service

🎤 How to Present This Project

Explain problem → data → ML → decision
Show predictions & probabilities
Explain AUC in simple terms
Highlight early risk detection

🏁 Final Note
This project demonstrates how raw data can be transformed into real-world decisions using Machine Learning, while maintaining explainability and business relevance.
