# Power BI Project – Agency Performance & Retention Analysis

## 📊 Project Overview
This Power BI project analyzes agency-level performance using metrics like **Written Premium**, **Retention Ratio**, **Loss Ratio**, and **Growth Rate**, helping identify the most consistent and profitable agencies across multiple years.

The dataset (`finalapi.csv`) includes agency, product line (CL/PL), and year-wise performance records, allowing deep dives into business trends from various perspectives.

---

## 🎯 Objectives
- Analyze agency performance and retention over time.
- Compare **Commercial Line (CL)** vs **Personal Line (PL)**.
- Identify **Top 10 Agencies/States** based on retention.
- Understand factors affecting **growth, loss ratio, and hit ratio**.
- Build a **clear, interactive Power BI dashboard** to visualize trends and KPIs.

---

## 🧩 Dataset Highlights
**Main columns used:**
- `AGENCY_ID`, `PRIMARY_AGENCY_ID`
- `STATE_ABBR`, `PROD_LINE`, `PROD_ABBR`
- `STAT_PROFILE_DATE_YEAR` (Year)
- `WRTN_PREM_AMT`, `PREV_WRTN_PREM_AMT`, `NB_WRTN_PREM_AMT`
- `RETENTION_RATIO`, `LOSS_RATIO`, `GROWTH_RATE_3YR`
- `ACTIVE_PRODUCERS`, `AGENCY_APPOINTMENT_YEAR`
- `CL_*` and `PL_*` columns (Hit Ratio, Quote Counts, Bound Counts)

**Data Cleaning:**
- Replaced all placeholder values `99999` → `null`.
- Adjusted column data types (e.g., Date, Decimal, Whole Number).
- Created a few new calculated columns:
  - `YEAR_DATE` (Date)
  - `HIT_FLAG` (Binary)
  - `POLICY_SIZE_BAND` (Text Category)

---

## 🧮 Measures Created
Key measures designed in DAX:

| Measure Name | Formula Description |
|---------------|---------------------|
| **Total Written Premium** | `SUM('finalapi'[WRTN_PREM_AMT])` |
| **Previous Premium** | `SUM('finalapi'[PREV_WRTN_PREM_AMT])` |
| **Growth %** | `(Total - Previous) / Previous` |
| **Retention Ratio** | `SUM('finalapi'[RETENTION_POLY_QTY]) / SUM('finalapi'[POLY_INFOR_CEL_QTY])` |
| **Loss Ratio** | `SUM('finalapi'[PRD_INCRD_LOSSES_AMT]) / [Total Written Premium]` |
| **Hit Ratio** | `SUM('finalapi'[HIT_FLAG]) / COUNTROWS('finalapi')` |
| **Total Active Producers** | `SUM('finalapi'[ACTIVE_PRODUCERS])` |

---

## 📈 Dashboard Insights
The dashboard includes multiple interactive visuals:
1. **Summary by Agency:** Retention %, Growth %, Loss Ratio, and Premium totals.
2. **Product Line Comparison:** CL vs PL performance across years.
3. **Top 10 Agencies and States:** Ranked by retention.
4. **Hit Ratio Distribution:** Across quote systems and product lines.
5. **Trend Lines:** Yearly growth and premium variation (2006–2013).
6. **Geo Visualization:** Retention ratio mapped by state.

---

## ⚙️ Tools & Techniques
- **Tool:** Power BI Desktop  
- **Languages:** DAX, Power Query (M)  
- **Techniques:** Data cleaning, Aggregations, Calculated Measures, KPI Cards, Top N Filters, Date Table Creation, Binning, and Interactive Slicers.  

---

## 📚 Learning Outcomes
- Building a star-schema model from raw data.
- Handling real-world inconsistencies (`99999` placeholders).
- Designing business-ready visuals and metrics.
- Understanding agency performance KPIs in insurance analytics.

---

## 🧠 Future Enhancements
- Add drill-through pages for individual agencies.
- Integrate forecasting visuals using historical retention data.
- Build a Power BI Service dashboard with automated refresh.

---

## 👨‍💻 Author
**Rakesh Aamalepatil**  
Data Analyst in Progress | Power BI Enthusiast  
📧 Connect: [LinkedIn](https://www.linkedin.com/in/rakeshaamalepatil)

---
