# Telecom Customer Churn Analysis — Power BI Dashboard

A Power BI dashboard analyzing customer churn for a telecom provider, built on a customer-level
dataset that has been pre-scored with a churn probability model. The report highlights *why*
customers churn, *who* is most at risk, and *what* the business should do about it.

## File

- `Dashboard.pbix` — Power BI Desktop file, 4 report pages

## Dataset

- **Source table:** `2-Telco-Customer-Churn-prob` (customer-level records, pre-scored with a churn
  probability / risk model before being loaded into Power BI)
- **Records:** 7,043 customers
- **Churned:** 1,869 customers (26.53%)

**Key fields**

| Field | Description |
|---|---|
| `customerID`, `gender`, `SeniorCitizen`, `Partner` | Customer identity & demographics |
| `tenure`, `Contract`, `PaperlessBilling`, `PaymentMethod` | Account & billing behavior |
| `PhoneService`, `InternetService`, `OnlineSecurity`, `DeviceProtection`, `TechSupport` | Services subscribed |
| `TotalCharges` | Cumulative revenue per customer |
| `Churn` | Actual churn flag (Yes/No) |
| `Churn_Prob`, `Risk` | Model-derived churn probability & risk classification |

## Dashboard Pages

1. **EDA (Exploratory Data Analysis)** — Univariate & bivariate breakdowns of churn (column,
   clustered-column, area charts) with summary cards for total records and churn count.
2. **Dashboard (Executive Summary)** — Side-by-side comparison of the full customer base
   ("Customer Profile") vs. the churned subset ("Churner Profile") using donut, pie, and
   clustered bar/column charts.
3. **Customers** — Slicer-driven, per-customer lookup showing personal info, services, contract,
   tenure, preferred payment mode, risk level, and churn probability.
4. **Churn Analysis** — Risk-focused action page quantifying the at-risk population and its
   revenue implication.

## Key Findings

- Gender has an approximately equal churn ratio (male 42.1% vs. female 42.7% within short-tenure
  contracts).
- Senior citizens churn at close to 50%, roughly double the overall rate.
- Churn decreases steadily as tenure increases (longer contracts → lower churn).
- **55.02%** of all customers prefer short tenure vs. **88.05%** of churned customers.
- **43.96%** of all customers use fiber-optic internet vs. **69.4%** of churned customers.
- Most churners lack online security and tech support add-ons.
- Electronic check is the most common payment method among both groups.
- **2,900 customers (41.2%)** are flagged high-risk; average risk score is **33.49**.

## Tools & Techniques

- Power BI Desktop — data modeling, DAX measures, KPI cards, 4-page report layout
- Upstream churn-probability / risk-scoring model (output merged into the customer table)
- Visual types: column, clustered column, clustered bar, donut, pie, area, card, slicer

## Recommendations

- Prioritize retention outreach to the 2,900 high-risk customers, starting with short-tenure,
  fiber-optic, electronic-check profiles.
- Bundle online security & tech support into onboarding offers.
- Incentivize longer-tenure contracts for new and at-risk customers.
- Track average risk score as a recurring KPI, targeting a reduction to ~16–17 (half of 33.49).

## How to Open

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Windows only).
2. Open `Dashboard.pbix`.
3. Use the page tabs at the bottom to navigate between EDA, Dashboard, Customers, and Churn
   Analysis.

## Related

- `Telecom_Churn_Dashboard_Report.pdf` — full written project report with charts and diagrams
