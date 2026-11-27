# DAX Measure Library – Audit Risk & Compliance Dashboard

All measures below are implemented to support executive KPIs, risk metrics, and departmental analytics.

> **Note on Table Referencing:** In the production Power BI Desktop report, the imported data table is named `'Deloitte_Audit_Data_Export_2026'` (matching the source CSV export). In generic documentation, it is aliased as `'Audit_Data'`. Both table references execute identically.

```dax
// 1. Total Claims Volume
Total Claims = COUNTROWS('Audit_Data')

// 2. Total Expenditure Amount (INR)
Total Amount = SUM('Audit_Data'[Amount_INR])

// 3. Approved Claims Volume
Approved Claims = 
CALCULATE(
    COUNTROWS('Audit_Data'),
    'Audit_Data'[Status] = "Approved"
)

// 4. Approved Amount (INR)
Approved Amount = 
CALCULATE(
    SUM('Audit_Data'[Amount_INR]),
    'Audit_Data'[Status] = "Approved"
)

// 5. Pending Approval Claims Volume
Pending Claims = 
CALCULATE(
    COUNTROWS('Audit_Data'),
    'Audit_Data'[Status] IN {"Submitted for Review", "Under Manager Review"}
)

// 6. Pending Amount (INR)
Pending Amount = 
CALCULATE(
    SUM('Audit_Data'[Amount_INR]),
    'Audit_Data'[Status] IN {"Submitted for Review", "Under Manager Review"}
)

// 7. Rejected Claims Volume
Rejected Claims = 
CALCULATE(
    COUNTROWS('Audit_Data'),
    'Audit_Data'[Status] = "Rejected"
)

// 8. High & Critical Risk Claims Volume
High Risk Claims = 
CALCULATE(
    COUNTROWS('Audit_Data'),
    'Audit_Data'[Risk_Level] IN {"HIGH", "CRITICAL"}
)

// 9. High Risk Exposure Rate
High Risk % = 
DIVIDE(
    [High Risk Claims],
    [Total Claims],
    0
)

// 10. Average Forensic Risk Score
Avg Risk Score = 
ROUND(AVERAGE('Audit_Data'[Risk_Score]), 1)

// 11. Average Transaction Claim Value
Avg Claim Value = 
DIVIDE([Total Amount], [Total Claims], 0)
```
