# 🟤 Bronze Layer – Raw Data Ingestion
🔍 Objective

The Bronze layer captures raw loan application data exactly as received from the source system.
No transformations are applied here.

-- 🧠 Why This Layer Exists

Preserves original data for auditing
Enables data lineage tracking
Prevents data loss or overwriting
Supports compliance & traceability

-- 🛠 What Happens Here

Load raw CSV / source data
Store data as Delta table
Maintain original schema
No cleaning, no filtering

-- 📥 Input
Raw loan dataset (demographics, income, loan details)

-- 📤 Output
Bronze Delta table with raw records

📌 Key Takeaway
“This layer ensures we always have the original truth of the data.”
