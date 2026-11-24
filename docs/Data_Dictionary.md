# Data Dictionary – Deloitte Audit & Risk Dataset

This data dictionary documents all fields exported from the **AuditVault – Enterprise Cloud Audit & Risk Governance Engine** and modeled in the Power BI dashboard.

| Column Name | Power BI Data Type | Business Meaning & Description | Sample Value |
| :--- | :--- | :--- | :--- |
| **`Tracking_Number`** | Text | Unique, immutable tracking code assigned to each audit request | `AUD-202611-27E2C145` |
| **`Employee_Username`** | Text | Corporate username of the submitter | `karishma_staff` |
| **`Employee_ID`** | Text | Enterprise employee identification code | `DEL-TECH-1042` |
| **`Department`** | Text | Business practice or operating unit | `Technology & Cloud Advisory`, `Forensic & Risk Consulting` |
| **`Title`** | Text | Description/title of the audit claim | `AWS High-Performance Cloud Cluster` |
| **`Category`** | Text | Expenditure category classification | `Software, Cloud & Tools`, `Client Meals & Engagement` |
| **`Amount_INR`** | Fixed Decimal / Currency | Financial value of the transaction in INR | `75000.00` |
| **`Currency`** | Text | ISO currency denomination code | `INR` |
| **`Status`** | Text | Current governance status | `Approved`, `Submitted for Review`, `Under Manager Review`, `Draft` |
| **`Risk_Score`** | Whole Number | Automated forensic score (0 to 100) computed by the risk engine | `60` |
| **`Risk_Level`** | Text | Risk classification tier (`LOW`, `MEDIUM`, `HIGH`, `CRITICAL`) | `HIGH` |
| **`Risk_Flags_Count`** | Whole Number | Total count of forensic policy triggers fired on this record | `3` |
| **`Risk_Flags_Summary`** | Text | Detailed pipe-separated description of triggered risk rules | `High transaction value exceeds ₹50,000 threshold...` |
| **`Submission_Date`** | Date/Time | Timestamp when the request was officially submitted | `2026-11-23 13:58:44` |
| **`Approving_Manager`** | Text | Name of the reviewing managerial authority | `Rahul Sharma` |
| **`Manager_Remarks`** | Text | Justification and audit review comments | `Verified against Q3 departmental policy.` |
