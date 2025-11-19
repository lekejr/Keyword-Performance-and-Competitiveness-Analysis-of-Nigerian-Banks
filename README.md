# Keyword Performance & Competitiveness Analysis of Nigerian Banks

> A data-driven SEO visibility analysis of major Nigerian banks using keyword data, CPC metrics, competition scores, and Power BI analytics.

---

## Table of Contents
1. [Introduction](#introduction)  
   1.1 [Background](#background)  
   1.2 [Objective](#objective)  
   1.3 [Scope of Analysis](#scope-of-analysis)  
2. [Data & Methodology](#data--methodology)  
   2.1 [Tools Used](#tools-used)  
   2.2 [Data Collection](#data-collection)  
   2.3 [Data Cleaning](#data-cleaning)  
   2.4 [Metrics & DAX Measures](#metrics--dax-measures)  
3. [Dashboard Overview](#dashboard-overview)  
4. [Insights & Analysis](#insights--analysis)  
   4.1 [Top 10 Keywords by Search Volume](#top-10-keywords-by-search-volume)  
   4.2 [Number of Keywords per Bank](#number-of-keywords-per-bank)  
   4.3 [Visibility Share (%)] (#visibility-share)  
   4.4 [Visibility Value per Bank](#visibility-value-per-bank)  
   4.5 [Average Competition vs Average CPC](#average-competition-vs-average-cpc)  
   4.6 [SEO Performance Index](#seo-performance-index)  
5. [Correlation Between SEO Visibility & Revenue](#correlation-between-seo-visibility--revenue)  
6. [Conclusion](#conclusion)  
7. [Recommendations](#recommendations)  
8. [Appendix](#appendix)

---

## Introduction

### Background
Search engine visibility has become a major driver of brand reach and customer acquisition in Nigeria’s increasingly digital banking landscape. A bank’s ability to rank for high-intent consumer keywords—such as *loans*, *savings accounts*, *online banking*, and *mobile apps*—strongly influences its organic traffic and market share.

This study evaluates the SEO visibility performance of major Nigerian banks to understand which brands dominate Google search results and what this reflects about their digital marketing strategies.

### Objective
The main objectives of this analysis are to:

- Evaluate Nigerian banks’ search engine visibility.  
- Determine which banks appear most frequently for consumer-focused banking keywords.  
- Assess keyword competitiveness and CPC value.  
- Examine potential relationships between SEO visibility and financial performance (revenue).

### Scope of Analysis
Focus areas include consumer-facing banking services:

- Online banking & internet banking  
- Loans & loan application queries  
- Savings & current accounts  
- Mobile banking apps & downloads  
- Credit cards & transfers

---

## Data & Methodology

### Tools Used
- **Power BI** — visualization & dashboarding  
- **WordStream (free keyword tool)** — keyword discovery & metrics  
- **Microsoft Excel (Power Query)** — data extraction & consolidation

### Data Collection
- Keywords were collected manually using the WordStream tool by searching each bank and relevant service queries.  
- Banks analyzed include: GTBank, UBA, Access Bank, Union Bank, Jaiz Bank, First Bank, Wema Bank, Sterling Bank, FCMB, Unity Bank, Keystone Bank, Polaris Bank, Ecobank (and others as available).  
- Each bank’s keyword export was combined into a master dataset using Excel Power Query.  
- Final dataset row count: **2,678 keywords**.

**Key columns captured**
- Keyword  
- Search Volume  
- Competition  
- Competition Index  
- Low Top Page Bid  
- High Top Page Bid  
- Bank Name

### Data Cleaning
Performed in Power BI and Excel Power Query:

- Trimmed, cleaned and standardized text fields.  
- Removed duplicate keyword rows (normalized keyword text).  
- Corrected data types (numeric for volumes/bids, text for keywords).  
- Imputed a small number of missing Competition Index values using column averages.  
- Validated and sampled exports to ensure bank attribution correctness.

### Metrics & DAX Measures
The following DAX measures were used in Power BI to drive KPIs and visuals:

```DAX
-- Basic aggregations
Total Search Volume = SUM([Search Volume])

Keyword Count = DISTINCTCOUNT([Keyword])

Average CPC = AVERAGE([High Top Page Bid])

Average Competition Index = AVERAGE([Competition Index])

-- Share and value measures
Visibility Share % =
DIVIDE([Keyword Count], CALCULATE([Keyword Count], ALL('Table'[Bank Name])))

Visibility Value =
SUMX('Table', [Search Volume] * [High Top Page Bid])

-- Composite performance metric
SEO Performance Index =
[Visibility Share %] * ([Average CPC] / [Average Competition Index])
```
## Dashboard Overview
The dashboard presents a unified, interactive analysis of keyword visibility, competitiveness, and brand dominance across major Nigerian banks. Visualizations highlight performance gaps and opportunities for organic growth.
<img width="1521" height="803" alt="Screenshot (741)" src="https://github.com/user-attachments/assets/6379b78e-87b3-4d87-988a-215c76ae9af5" />

**Dashboard components**
- 5 KPI cards (Total Search Volume, Total Keywords, Average CPC, Top Bank by Visibility, Total Visibility Value)  
- Top Keywords bar chart (by search volume)  
- Keywords per Bank stacked bar chart  
- Visibility Share pie chart  
- Visibility Value ranking (by bank — monetary estimate)  
- CPC vs Competition scatter plot  
- SEO Performance Index ranking table  
- Drillthrough page for keyword-level details and raw exports

---

## Insights & Analysis

### Top 10 Keywords by Search Volume
High-volume queries are dominated by general digital banking terms such as *online banking*, *internet banking*, *bank mobile app*, and *loan application*. GTBank, UBA, and Access Bank appear most frequently across these high-intent terms, indicating strong brand recognition in digital banking search intent.

###  Number of Keywords per Bank
- **Union Bank** — ~500 unique keywords (largest breadth)  
- **GTBank** — ~368 unique keywords  
- **Sterling Bank** — ~315 unique keywords

Interpretation: Union Bank targets a wider set of keywords (breadth), while GTBank focuses on fewer, higher-volume or higher-value keywords (depth).

###  Visibility Share (%)
Top shares (approximate):
- **Union Bank** — **19%** of keyword share  
- **GTBank** — **11%**  
- **UBA** — **11%**

These three banks together account for **>40%** of monitored keywords.

###  Visibility Value per Bank
Visibility Value approximates the hypothetical paid-ad cost for capturing organic query volume at the observed CPC:

| Bank     | Visibility Value (₦) |
|----------|----------------------:|
| UBA      | ₦2,640,000           |
| GTBank   | ₦1,350,000           |
| Access   | ₦765,000             |

Interpretation: UBA’s keyword set includes many high-intent, high-value commercial terms, making organic visibility highly valuable.

###  Average Competition vs Average CPC
- Dataset shows a **moderately competitive** landscape.  
- Example averages: Competition Index ≈ **2.15**, Average CPC ≈ **2.27**.  
- GTBank and Access Bank operate in higher-CPC keyword segments, suggesting either strong paid competition or greater commercial intent.

### SEO Performance Index
Composite index combining visibility share, CPC and competition:

| Bank       | SEO Performance Index |
|------------|----------------------:|
| UBA        | 0.54                 |
| Union Bank | 0.37                 |
| GTBank     | 0.27                 |

Interpretation: UBA leads by balancing visibility with high-value keyword exposure. Union Bank has breadth but lower CPC-weighted value. GTBank focuses on high-impact keywords but ranks below UBA on the composite metric.

---

##  Correlation Between SEO Visibility & Revenue
- A positive correlation is observed between claimed revenue levels and SEO visibility for large banks (UBA, GTBank, Access).  
- **Union Bank** demonstrates strong organic keyword coverage despite lower reported revenue — an example of content-driven SEO outperforming expectations.  
- Conclusion: While revenue and SEO strength often align, smaller banks can secure strong organic visibility with good content strategy and targeted keyword coverage.

---

##  Conclusion
- **UBA** ranks top for SEO Performance Index and Visibility Value — leading in high-value keyword exposure.  
- **Union Bank** leads on keyword breadth, suggesting a content-first strategy.  
- **GTBank** dominates app- and digital banking-related searches.  
- Mid-tier banks can achieve efficient organic gains by focusing on long-tail, lower-competition transactional keywords.

---

##  Recommendations
1. **Prioritise transactional landing pages** for high-CPC, high-intent keywords (e.g., "loan application", "open account online").  
2. **Leverage CPC to align SEO & SEM budgets** — bid where CPC indicates immediate commercial intent while building organic content for long-term ROI.  
3. **Expand long-tail content** for mid-tier banks to capture low-competition, high-conversion queries.  
4. **Implement routine keyword tracking** and monthly visibility audits.  
5. **Create product-led content pillars** (loans, account opening, app features) and optimize landing pages to convert organic traffic to signups.  
6. **Measure SEO outcomes against business KPIs** (account openings, loan applications) to link visibility to revenue.

---

##  Appendix

**Raw dataset summary**
- Total keywords: **2,678** (merged WordStream exports)  
- Banks included (sample): GTBank, UBA, Access Bank, Union Bank, Jaiz Bank, First Bank, Wema Bank, Sterling Bank, FCMB, Unity Bank, Keystone Bank, Polaris Bank, Ecobank

**Tools**
- WordStream (keyword discovery)  
- Excel Power Query (merge & transform)  
- Power BI (visualization & DAX)

**DAX Measures**
```DAX
Total Search Volume = SUM([Search Volume])

Keyword Count = DISTINCTCOUNT([Keyword])

Average CPC = AVERAGE([High Top Page Bid])

Average Competition Index = AVERAGE([Competition Index])

Visibility Share % =
DIVIDE([Keyword Count], CALCULATE([Keyword Count], ALL('Table'[Bank Name])))

Visibility Value =
SUMX('Table', [Search Volume] * [High Top Page Bid])

SEO Performance Index =
[Visibility Share %] * ([Average CPC] / [Average Competition Index])
