# 🏥 Healthcare Provider Fraud Detection

![Project Workflow](image.webp)


## 📌 Summary

Fraudulent activities in healthcare insurance claims lead to significant financial losses and inflated insurance premiums. This project focuses on identifying **potentially fraudulent providers** using historical insurance claim data, aiming to help insurers minimize risk and reduce costs.

---

## 🎯 Objective

- Predict potentially **fraudulent providers** based on historical claim patterns.
- Identify key variables and features that contribute most to detecting fraud.
- Explore fraudulent behavior and trends among providers to anticipate future risks.
- Deliver business insights and recommendations to improve fraud detection systems.

---

## 🔁 Workflow

1. **Data Management**
   - Load and merge Inpatient, Outpatient, and Beneficiary datasets.
   - Handle missing values, date formatting, and data types.

2. **Exploratory Data Analysis (EDA)**
   - Analyze provider-wise claim trends.
   - Study diagnosis/procedure codes and their frequency.
   - Explore demographic and geographic patterns.

3. **Feature Engineering**
   - Generate new features (e.g., total claim duration, number of procedures, chronic condition counts).
   - Encode categorical variables and normalize numerical ones.

4. **Feature Selection**
   - Correlation matrix and feature importance ranking.
   - Remove redundant or low-information features.

5. **Model Building**
   - Train multiple models (e.g., Random Forest, XGBoost, Logistic Regression).
   - Tune hyperparameters using cross-validation.

6. **Evaluation**
   - Evaluate using precision, recall, F1-score, AUC-ROC.
   - Compare model performances.

7. **Business Recommendations**
   - Suggest control policies based on model findings.
   - Propose audit strategy based on provider risk scores.

---

## 📊 Business Insights

- A small fraction of providers contributes disproportionately to fraudulent claims.
- Ambiguous or rare diagnosis and procedure codes often correlate with fraud.
- Repeated high-cost claims and unusually short or long hospital stays can be fraud indicators.
- Geographic clusters and specific physician behavior may indicate organized fraud rings.

---

## 🧬 Column Descriptions

| Column | Description |
|--------|-------------|
| `BeneID` | Unique ID for each beneficiary (patient). |
| `ClaimID` | Unique identifier for each claim submitted. |
| `ClaimStartDt`, `ClaimEndDt` | Start and end dates of the medical claim. |
| `Provider` | Unique identifier for the healthcare provider. |
| `InscClaimAmtReimbursed` | Amount reimbursed to the provider. |
| `AttendingPhysician`, `OperatingPhysician`, `OtherPhysician` | Physicians involved in the claim. |
| `AdmissionDt`, `DischargeDt` | Dates of admission and discharge (inpatient). |
| `ClmAdmitDiagnosisCode` | Primary diagnosis code upon admission. |
| `DiagnosisGroupCode` | Group category for diagnosis codes. |
| `ClmDiagnosisCode_1` to `ClmDiagnosisCode_10` | Up to 10 diagnosis codes for the claim. |
| `ClmProcedureCode_1` to `ClmProcedureCode_6` | Procedure codes billed in the claim. |
| `DeductibleAmtPaid` | Amount paid out-of-pocket by beneficiary. |
| `DOB`, `DOD` | Date of birth and (if applicable) date of death of the beneficiary. |
| `Gender` | Gender of the beneficiary. |
| `Race` | Race category of the beneficiary. |
| `RenalDiseaseIndicator` | Indicates if the beneficiary has renal disease. |
| `State`, `County` | Geographic location of the beneficiary. |
| `NoOfMonths_PartACov`, `NoOfMonths_PartBCov` | Medicare coverage months under Part A and B. |
| `ChronicCond_*` | Binary indicators of various chronic conditions (e.g., Alzheimer's, Diabetes). |
| `IPAnnualReimbursementAmt`, `OPAnnualReimbursementAmt` | Annual inpatient/outpatient reimbursements. |
| `IPAnnualDeductibleAmt`, `OPAnnualDeductibleAmt` | Annual deductible paid for IP/OP services. |
| `PotentialFraud` | Target variable (Yes/No) indicating potential fraud. |
| `Age` | Age of the beneficiary (derived from DOB). |

---

## ✅ Deliverables

- Preprocessed datasets ready for modeling.
- Trained models with performance metrics.
- Feature importance and pattern analysis.
- Business insights and action recommendations.
- Submission file with predictions on test data.

---

## 💡 Tools & Technologies

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn, XGBoos, Random Forest, Logistic Regressiont
- Jupyter Notebook
- Git for version control

---

## 📈 Evaluation Criteria

- Accuracy, Precision, Recall, F1-Score, AUC-ROC
- Relevance and interpretability of features
- Actionable insights and business recommendations

---

## 🔮 Future Scope

This project lays the groundwork for scalable and intelligent fraud detection systems in healthcare. Future developments can include:

- **Real-time Fraud Detection:**  
  Integrate the trained model with claim submission pipelines to flag potentially fraudulent providers in real time, enabling proactive action.

- **Explainable AI (XAI):**  
  Leverage techniques like SHAP (SHapley Additive exPlanations) or LIME (Local Interpretable Model-agnostic Explanations) to make model decisions interpretable for compliance officers and stakeholders.

- **Graph-Based Analysis:**  
  Use network/graph theory to model relationships between providers, patients, and procedures to uncover hidden fraud rings or collusion patterns.

- **Temporal and Sequential Modeling:**  
  Incorporate claim history over time using time-series models or LSTMs to capture evolving fraud patterns.

- **AutoML and Ensemble Methods:**  
  Utilize AutoML tools to automatically select and tune high-performing models, or combine multiple models in an ensemble to improve robustness.

- **Interactive Dashboards:**  
  Develop real-time monitoring dashboards for insurers to visualize fraud risk by provider, region, or claim type.

- **Feedback Loop for Continuous Learning:**  
  Retrain models periodically with feedback from audits and investigations to improve detection accuracy over time.

- **Integration with External Data:**  
  Include external datasets such as provider reviews, public sanctions, and geographic statistics to enrich the fraud detection pipeline.

- **Policy and Audit Optimization:**  
  Use risk scores from the model to design targeted audit strategies and customized insurance policies for high-risk providers.

