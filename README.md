# 🛡️ Insurance Claims Risk, Data Quality & Process Analytics

![Python](https://img.shields.io/badge/Python-Analytics-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Data Quality](https://img.shields.io/badge/Data%20Quality-Validation-2E8B57)
![Insurance](https://img.shields.io/badge/Domain-Insurance-6F42C1)
![Risk Analytics](https://img.shields.io/badge/Risk-Analytics-C62828)
![Business Analysis](https://img.shields.io/badge/Business-Analysis-E67E22)
![UAT](https://img.shields.io/badge/UAT-Validated-455A64)

## 📌 Project Overview

This project analyzes a **synthetic insurance claims portfolio** from three connected perspectives: **data quality, claims operations, and risk prioritization**.

Rather than focusing only on dashboarding, the project demonstrates an end-to-end analytical workflow covering **business-rule validation, data-quality exception management, claims lifecycle analysis, root-cause analysis, transparent risk indicators, business requirements, UAT, and process improvement**.

> **Portfolio note:** The dataset is synthetic and was created solely for portfolio and analytical demonstration purposes.

---

## 🎯 Business Objectives

| Objective | Business Question |
|---|---|
| 🔍 Data Quality | Can the claims data be trusted for downstream analysis and reporting? |
| ⏱️ Settlement Performance | Which policy/region segments show settlement delays? |
| ❌ Rejections | What are the major recorded rejection reasons? |
| 🔁 Repeat Claims | Does repeat-claim behavior show a different risk profile? |
| 🛡️ Risk Prioritization | Which claims should be prioritized for further review? |
| ⚙️ Process Improvement | Which controls can improve claims operations and data quality? |

---

## 🗂️ Dataset Snapshot

| Metric | Value |
|---|---:|
| Raw Claims | **5,000** |
| Analysis-Ready Claims | **4,854** |
| Records with ≥1 DQ Exception | **208 (4.16%)** |
| Analytical Exclusions for Critical Issues | **146** |
| Total Claimed Amount | **~₹25.78 Cr** |
| Total Approved Amount | **~₹14.66 Cr** |

---

## 🧹 Data Quality Assessment

The business-rule-driven validation identified the following exceptions:

| Data Quality Rule | Exceptions |
|---|---:|
| Duplicate Claim IDs | **25 IDs / 50 affected rows** |
| Missing Policy IDs | **35** |
| Missing Customer IDs | **20** |
| Missing Provider IDs | **25** |
| Approved Amount > Claim Amount | **24** |
| Settlement Date < Claim Date | **15** |
| Rejected Claim Missing Rejection Reason | **30** |
| Invalid Claim Amount | **6** |
| Invalid Premium Amount | **6** |

### 🔎 Important Data-Quality Decision

The duplicated Claim IDs were **not automatically deleted** because the analysis found **no exact duplicate rows**. They were retained as **identifier/key-integrity exceptions** for source-system investigation rather than treated as redundant records.

---

## 📊 Key Business Findings

| Area | Finding |
|---|---|
| 💰 **Claims Exposure** | Health generated the highest aggregate claim exposure at **~₹9.93 Cr**, while Home recorded the highest average claim value at **~₹77,975**. |
| ⏱️ **Settlement Performance** | Travel recorded the highest overall delay rate at **64.34%** using a 30-day analytical threshold. |
| 📍 **Operational Hotspot** | Travel claims in the South region had **60 settled claims**, **47.67 average settlement days**, and a **76.67% delay rate**. |
| ❌ **Rejection Analysis** | Coverage Limit was the most common recorded rejection reason (**131 claims**), followed by Late Notification (**120**) and Suspected Misrepresentation (**119**). |
| 🔁 **Repeat Claims** | Repeat claims had an average risk score of **3.48** versus **1.51** for non-repeat claims, despite not having a higher average claim amount. |
| 🛡️ **Risk Prioritization** | **256 claims (5.27%)** were classified as High Risk for further review. |
| 📈 **Claim Severity** | IQR analysis identified **284 claim-value outliers** above approximately **₹130,888**. |

> **Important:** “High Risk” represents rule-based prioritization for further investigation. It does **not** mean confirmed fraud.

> **SLA note:** The 30-day settlement threshold is an analytical assumption for this case study and should not be interpreted as an insurer's contractual SLA.

---

## 🛡️ Transparent Risk-Prioritization Framework

The project uses interpretable business rules rather than a black-box fraud classification model.

| Risk Segment | Claims |
|---|---:|
| 🟢 Low | **3,340** |
| 🟠 Medium | **1,258** |
| 🔴 High | **256** |

Risk indicators include repeat-claim behavior, early-policy claims, unusually high claim-to-premium ratios, high-value claims, and reporting delays.

---

## 🔁 Repeat-Claim Analysis

| Segment | Claims | Avg. Claim Amount | Avg. Risk Score |
|---|---:|---:|---:|
| Non-Repeat | **3,933** | **₹53,357.96** | **1.51** |
| Repeat | **921** | **₹52,050.56** | **3.48** |

**Interpretation:** Repeat-claim behavior did not correspond to higher average claim value, but it was associated with a substantially higher rule-based risk score. It is therefore treated as a **review indicator**, not a standalone fraud signal.

---

## 📋 Business Analysis Deliverables

- ✅ Business Requirements (BR-01 to BR-06)
- ✅ User Stories & Acceptance Criteria
- ✅ As-Is Claims Process
- ✅ Proposed To-Be Claims Process
- ✅ Gap & Root-Cause Analysis
- ✅ 8 UAT Scenarios
- ✅ Requirements Traceability Matrix (RTM)
- ✅ Data-Quality Exception Reporting
- ✅ Business Recommendations

### As-Is → To-Be

**As-Is**

`Claim Submitted → Manual Data Validation → Document Review → Claim Assessment → Approval/Rejection → Settlement → Reporting`

**Proposed To-Be**

`Claim Submitted → Automated DQ Validation → Critical Exception Queue → Rule-Based Risk Assessment → Review/Prioritization → SLA Monitoring → Approval/Rejection → Settlement → DQ/Operational Monitoring`

---

## 🧪 UAT Coverage

Eight UAT scenarios validate:

- Duplicate Claim ID handling
- Missing Policy ID detection
- Financial consistency
- Claim lifecycle/date consistency
- Settlement delay flag
- Rejection-reason completeness
- Risk-indicator logic
- Repeat-claim logic

The RTM maps **BR-01 through BR-06** to the corresponding analysis and validation coverage.

---

## 💡 Business Recommendations

1. Introduce automated data-quality controls before claims enter downstream reporting.
2. Route critical DQ exceptions to a dedicated review queue rather than silently dropping records.
3. Monitor settlement delays proactively at policy, region, and provider levels.
4. Use transparent risk indicators to prioritize manual review without labeling claims as fraud.
5. Standardize mandatory rejection-reason capture.
6. Separate raw, exception, and analysis-ready datasets to preserve auditability.
7. Define ownership and remediation workflows for recurring data-quality issues.

---

## 🛠️ Tools & Skills

`Python` • `Pandas` • `NumPy` • `Google Colab` • `Data Quality` • `Insurance Analytics` • `Risk Analytics` • `Business Analysis` • `Root Cause Analysis` • `UAT` • `Process Improvement`

---

## 📁 Repository Structure

```text
insurance-claims-risk-data-quality-analytics/
│
├── README.md
│
├── business analysis/
│   ├── requirements_traceability_matrix.csv
│   └── uat_test_cases.csv
│
├── data/
│   ├── insurance_claims_case_study.csv
│   └── claims_analysis_ready.csv
│
├── notebook/
│   └── Insurance_Claims_Risk_Analytics.ipynb
│
└── outputs/
    ├── data_quality_report.csv
    ├── data_quality_exceptions.csv
    └── high_risk_claims_for_review.csv
```

---

## 🚀 Key Takeaway

This case study demonstrates how **data analytics, data quality, risk analysis, and business analysis** can work together to improve insurance claims operations.

The project goes beyond identifying patterns: it translates analytical findings into **business requirements, validation controls, UAT scenarios, traceability, and process-improvement recommendations**.
