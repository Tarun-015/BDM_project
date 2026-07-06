# Product Requirements Document (PRD)

## 1. Document Information

| Field    | Details                                      |
| -------- | -------------------------------------------- |
| Project  | Retail Sales & Inventory Analytics Dashboard |
| Business | Maa Vindhyawasini Marble                     |
| Author   | Tarun Chaudhary                              |
| Sponsor  | Mr. Shahul Saraf                             |
| Date     | Jan 2026                                    |
| Status   | Draft                                        |

---

# 2. Problem Statement

### Current Challenges

* Business decisions rely primarily on manual records and experience.
* Sales trends are not analyzed systematically.
* Slow-moving inventory cannot be identified easily.
* Purchasing decisions are made without historical analysis.
* No centralized dashboard exists for monitoring business performance.

---

# 3. Background

Maa Vindhyawasini Marble is a family-owned tiles, marble, and sanitaryware dealership in Ghazipur, Uttar Pradesh, operating for more than 20 years. The business is an authorized Varmora dealer and has been managed by **Mr. Shahul Saraf**, the second-generation owner, for the past four to five years. As inventory and product variety increased, the need for data-driven decision making became evident. This project analyzes five years of sales and purchase data to support inventory planning and business decisions through an interactive Power BI dashboard.

---

# 4. Objectives

* Analyze five years of sales and purchase data.
* Identify revenue trends.
* Perform ABC Analysis.
* Perform FSN Analysis.
* Calculate EOQ and Reorder Point.
* Develop an interactive Power BI dashboard.
* Generate actionable business recommendations.

---

# 5. Success Metrics

| Metric                             | Target    |
| ---------------------------------- | --------- |
| Historical data prepared           | ✓         |
| Sales trend analysis completed     | ✓         |
| ABC Analysis completed             | ✓         |
| FSN Analysis completed             | ✓         |
| EOQ & ROP generated                | ✓         |
| Interactive dashboard developed    | ✓         |
| Business recommendations delivered | Minimum 3 |

---

# 6. Stakeholders

| Stakeholder            | Role            |
| ---------------------- | --------------- |
| Mr. Shahul Saraf       | Project Sponsor |
| Tarun Chaudhary        | Developer       |
| IIT Madras BDM Faculty | Reviewer        |

---

# 7. Users

| User           | Purpose                                     |
| -------------- | ------------------------------------------- |
| Business Owner | Monitor sales and inventory performance     |
| Store Manager  | Inventory monitoring and purchasing support |

---

# 8. Scope

### In Scope

* Data Cleaning
* Sales Analysis
* Inventory Analysis
* ABC Classification
* FSN Classification
* EOQ Calculation
* Reorder Point Calculation
* Power BI Dashboard
* Business Recommendations

### Out of Scope

* ERP Integration
* Live Dashboard
* Automated Procurement
* Machine Learning Forecasting
* Customer Analytics

---

# 9. Functional Requirements

| ID    | Requirement                                |
| ----- | ------------------------------------------ |
| FR-01 | Import sales and purchase data from Excel. |
| FR-02 | Clean and standardize business data.       |
| FR-03 | Display monthly and yearly sales trends.   |
| FR-04 | Perform category-wise sales analysis.      |
| FR-05 | Perform ABC Analysis.                      |
| FR-06 | Perform FSN Analysis.                      |
| FR-07 | Calculate EOQ.                             |
| FR-08 | Calculate Reorder Point.                   |
| FR-09 | Display KPIs and charts in Power BI.       |
| FR-10 | Export dashboard reports.                  |

---

# 10. Non-Functional Requirements

| ID     | Requirement                                   |
| ------ | --------------------------------------------- |
| NFR-01 | Dashboard should load within 5 seconds.       |
| NFR-02 | Dashboard should be easy to understand.       |
| NFR-03 | Data should remain stored locally.            |
| NFR-04 | Dashboard should support future data refresh. |
| NFR-05 | Compatible with Power BI Desktop.             |

---

# 11. Dashboard Modules

| Module              | Description                           |
| ------------------- | ------------------------------------- |
| Overview            | KPIs, Revenue Trend                   |
| Sales Analysis      | Monthly, Yearly and Category Analysis |
| Product Performance | Top and Bottom Products               |
| Inventory           | ABC & FSN Analysis                    |
| Inventory Planning  | EOQ & ROP                             |
| Recommendations     | Business Insights                     |

---

# 12. Data Sources

| Source              | Description                   |
| ------------------- | ----------------------------- |
| Sales Register      | Historical sales transactions |
| Purchase Register   | Purchase records              |
| Product Master      | Product categories            |
| Business Discussion | Inputs from Mr. Shahul Saraf  |

---

# 13. User Flow

```text
Sales & Purchase Data
          │
          ▼
    Data Cleaning
          │
          ▼
 Exploratory Analysis
          │
          ▼
Inventory Analysis
 (ABC, FSN, EOQ, ROP)
          │
          ▼
 Power BI Dashboard
          │
          ▼
Business Recommendations
```

---

# 14. Project Timeline

<img width="958" height="376" alt="image" src="https://github.com/user-attachments/assets/f5c09e98-1876-4e10-b844-5b2976267dbf" />


---

# 15. Risks

| Risk                          | Mitigation                    |
| ----------------------------- | ----------------------------- |
| Missing records               | Validate during preprocessing |
| Inconsistent product names    | Standardize during cleaning   |
| Limited business availability | Schedule review meetings      |
| Time constraints              | Prioritize core deliverables  |

---

# 16. Acceptance Criteria

| ID    | Criteria                           |
| ----- | ---------------------------------- |
| AC-01 | Historical dataset prepared        |
| AC-02 | Dashboard completed                |
| AC-03 | Sales analysis completed           |
| AC-04 | Inventory analysis completed       |
| AC-05 | EOQ & ROP generated                |
| AC-06 | Business recommendations submitted |

---

# 17. Future Enhancements

* Demand forecasting
* Supplier analytics
* Profitability analysis
* Mobile dashboard
* Automated inventory alerts
* ERP integration

---

# 18. References

* IIT Madras BDM Capstone Guidelines
* Business Records: Maa Vindhyawasini Marble
* Microsoft Power BI Documentation
* Python Documentation (Pandas, NumPy)
* Standard Inventory Management Techniques (ABC, FSN, EOQ, ROP)
