# Insurance Claims Risk, Data Quality & Process Analytics

## Project Overview

This project analyzes a synthetic insurance claims portfolio from three connected perspectives: data quality, claims operations, and risk prioritization.

The project demonstrates an end-to-end analytical workflow covering business-rule validation, data-quality exception management, claims lifecycle analysis, root-cause analysis, transparent risk indicators, business requirements, UAT, and process improvement.

## Business Objectives

- Assess the reliability of claims data
- Identify drivers of settlement delays
- Analyze rejection patterns
- Identify claims requiring additional risk review
- Analyze repeat-claim behavior
- Identify operational bottlenecks
- Recommend data-quality and process controls

## Dataset

- Raw claims: 5,000
- Analysis-ready claims: 4,854
- Data-quality exception records: 208
- Analytical exclusions due to critical issues: 146

The dataset used in this project is synthetic and was created solely for portfolio and analytical demonstration purposes.

## Data Quality Findings

A business-rule-driven data-quality assessment identified:

- 25 duplicated Claim IDs affecting 50 records
- 35 missing Policy IDs
- 20 missing Customer IDs
- 25 missing Provider IDs
- 24 records where approved amount exceeded claimed amount
- 15 records with settlement dates preceding claim dates
- 30 rejected claims without a rejection reason
- 6 invalid claim amounts
- 6 invalid premium amounts

4.16% of records contained at least one identified data-quality exception.

Duplicate Claim IDs were not automatically deleted because no exact duplicate rows existed. They were retained as identifier-integrity exceptions for source-system investigation.

## Key Business Findings

### Claims Exposure

The analysis-ready portfolio contained 4,854 claims representing approximately ₹25.78 crore in claimed value and ₹14.66 crore in approved value.

Health insurance generated the highest aggregate claim exposure at approximately ₹9.93 crore, while Home insurance recorded the highest average claim value at approximately ₹77,975.

### Settlement Performance

Using a 30-day analytical threshold, Travel claims recorded the highest overall delay rate at 64.34%.

The strongest policy-region hotspot was Travel claims in the South region:

- 60 settled claims
- 47.67 average settlement days
- 46 delayed claims
- 76.67% delay rate

The 30-day threshold is an analytical assumption used for this case study and should not be interpreted as a contractual insurer SLA.

### Rejection Analysis

Coverage Limit was the most common recorded rejection reason with 131 claims, followed by Late Notification (120) and Suspected Misrepresentation (119).

30 rejected claims had no rejection reason, highlighting a data-quality and process-control issue affecting rejection reporting.

### Repeat-Claim Behavior

Repeat-claim records did not show higher average claim amounts. However, their average rule-based risk score was 3.48 compared with 1.51 for non-repeat claims, supporting repeat behavior as a review indicator rather than a standalone fraud signal.

### Risk Prioritization

The transparent rule-based framework classified:

- 3,340 claims as Low risk
- 1,258 claims as Medium risk
- 256 claims as High risk

High-risk classification represents prioritization for further investigation and does not indicate confirmed fraud.

### Claim Severity

IQR analysis identified 284 claim-value outliers above approximately ₹130,888.

The largest claim was approximately ₹974,192. The analysis demonstrates that claim severity and analytical risk classification should be evaluated separately.

## Business Analysis Deliverables

The project includes:

- Business requirements
- User stories and acceptance criteria
- As-Is claims process
- Proposed To-Be process
- Root-cause analysis
- 8 UAT scenarios
- Requirements Traceability Matrix
- Data-quality exception reporting
- Business recommendations

## Tools & Skills

Python | Pandas | NumPy | Google Colab | Data Quality | Insurance Analytics | Risk Analytics | Business Analysis | Root Cause Analysis | UAT | Process Improvement

## Repository Structure

```text
├── README.md
├── data/
│   ├── raw/
│   │   └── insurance_claims_case_study.csv
│   └── processed/
│       └── claims_analysis_ready.csv
├── notebook/
│   └── Insurance_Claims_Risk_Analytics.ipynb
├── outputs/
│   ├── data_quality_report.csv
│   ├── data_quality_exceptions.csv
│   └── high_risk_claims_for_review.csv
└── business_analysis/
    ├── requirements_traceability_matrix.csv
    └── uat_test_cases.csv
```

## Key Takeaway

This project demonstrates how data quality, business analysis, and analytical reasoning can be combined to improve insurance claims operations, identify process bottlenecks, and prioritize records for further review without treating analytical risk indicators as confirmed fraud.
