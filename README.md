# MobileImpact: Cross-Channel Donor, Revenue & Campaign Analytics (BigQuery SQL)

**Executive Summary**
MobileImpact is an end-to-end, industry-style analytics case study that designs and implements a production-ready analytics layer to understand donor behaviour, revenue performance, and marketing effectiveness across traditional donation channels and mobile in-app purchases.

Using Google BigQuery (SQL only), this project:

- Cleans and standardises raw operational data
- Builds an analytics-ready data model
- Produces decision-grade KPIs for revenue, donors, campaigns, and engagement
- Delivers segmentation, attribution, and risk analysis
- Translates results into measurable business recommendations

The business context and datasets are based on an industry-style academic brief from Deakin University, but the implementation is designed and executed as a real-world analytics project suitable for Data Analyst / Business Analyst / BI roles.

**Business Context & Problem Statement**
The organisation operates across two monetisation ecosystems:

- Traditional donations (products, payment channels, recurring gifts)
- Mobile in-app purchases (games, devices, spending segments, session behaviour)

Leadership needs to answer strategic questions such as:

1. Are mobile and traditional channels complementary or cannibalising each other?
2. Which donor segments and behaviours drive the majority of revenue?
3. How effective are marketing campaigns in generating engagement and monetisation?
4. Where should budget be allocated to maximise ROI and lifetime value?
5. Which donors are high value, and which are at risk of churn?

**Core Objective**
Design a **scalable analytics layer** and deliver **decision-ready insights** across:

- Channel performance
- Customer value & segmentation
- Product / content performance
- Campaign effectiveness & ROI
- Retention risk & growth opportunities

**Data Sources**

Provided via **Deakin University** industry-style brief (included in this repository):

- Customers.csv – Demographics, household attributes
- Tradition_Donation_Patterns.csv – Traditional donation transactions
- Mobile_Game_Inapp_Purchases.csv – Mobile in-app purchase behaviour
- Marketing_Campaigns.csv – Campaign metadata (type, date, budget, targeting)
- Campaign_Response.csv – Campaign responses, CTR, engagement metrics

These were ingested into Google BigQuery as raw tables:
1. customers_raw
2. traditional_raw
3. mobile_raw
4. campaigns_raw
5. campaign_response_raw

**Analytics Architecture & Data Pipeline**

**1. Ingestion**

- CSV → BigQuery raw tables

**2. Data Cleaning & Standardisation (SQL)**

- Type coercion, schema normalisation, null handling
- Created curated tables:
  1. customers_clean
  2. traditional_clean
  3. mobile_clean
  4. campaigns_clean
  5. response_clean

**3. Analytical Modelling**
- Cross-channel customer views
- Per-customer revenue aggregation
- Campaign attribution windows (30-day post-campaign)
- Behavioural segmentation (recurring, high-value, at-risk)

**4. KPI & Insight Layers**
- Channel performance summaries
- Donor overlap & cross-channel behaviour
- Product, genre, device, and payment analysis
- Campaign response, engagement, ROI
- Retention risk & high-value donor profiling

**5. Outputs**
- All major analytical tables exported as CSV for dashboards and reporting (included in repo)

**Data Model (Conceptual)**
**Entities**
1. customers_clean → customer demographics & profile
2. traditional_clean → donation transactions
3. mobile_clean → in-app purchase transactions
4. campaigns_clean → campaign metadata
5. response_clean → campaign response & engagement

**Relationships**
1. customer_id links customers ↔ transactions ↔ responses
2. campaign_id links campaigns ↔ responses
- Analytical views combine customer × channel × time × campaign

**This structure supports:**
- Cross-channel attribution
- Customer lifetime value analysis
- Campaign ROI modelling
- Behavioural segmentation at scale

**Business Questions Answered**

**Channel & Revenue Strategy**
1. How do traditional vs mobile compare in:
- Revenue, donors, transactions, average gift size?

2. What proportion of donors are:
- Traditional-only, mobile-only, or cross-channel?

**Customer Value & Behaviour**
1. Who are the top 10% high-value donors?
2. How does recurring vs one-off behaviour affect revenue?
3. How long does it take users to make their first mobile purchase?
4. Which donors are at risk based on inactivity windows?

**Product & Content Performance**
1. Which products, game genres, devices, and payment methods drive revenue?
2. Where is revenue concentration vs long-tail performance?

**Marketing & Campaign Effectiveness**
1. Which campaigns generate the highest response rates and engagement?
2. What is the 30-day revenue attribution and ROI per campaign?
3. Does higher spend correlate with better performance?

**Segmentation & Demographics**
1. How do gender, income, location affect channel usage and value?
2. Which segments prefer which channels and products?

**KPIs Produced**

**Channel KPIs**
- Total revenue, donors, transactions
- Average gift / purchase value
- Cross-channel overlap ratios

**Customer KPIs**
- Revenue per customer (by channel & total)
- Transaction frequency
- High-value donor deciles
- At-risk donor counts

**Product & Content KPIs**
- Revenue by product & payment channel
- Revenue by game genre
- Revenue by device & payment method

**Campaign KPIs**
- Response rate
- Average CTR
- Engagement frequency
- 30-day attributed revenue
- Campaign ROI

**Key Analytical Findings (Evidence-Based)**
1. Revenue is highly concentrated in a small high-value donor segment (top decile).
2. Recurring donors exhibit materially higher lifetime value than one-off donors.
3. Mobile and traditional channels show partial overlap, indicating distinct behavioural segments.
4. Time-to-first-purchase analysis highlights early lifecycle activation as a critical monetisation lever.
5. Campaign ROI varies significantly: targeting and engagement quality matter more than raw spend.
6. Product, genre, device, and payment analysis reveal clear optimisation opportunities for content and UX strategy.
7. A non-trivial cohort of donors shows inactivity risk, enabling proactive retention strategies.

**Business Recommendations (Conservative & Actionable)**
1. Prioritise retention and upsell of high-value and recurring donors.
2. Use early behavioural signals to trigger personalised mobile monetisation journeys.
3. Reallocate campaign budgets using ROI-based ranking, not just response rates.
4. Develop channel-specific strategies instead of a single unified donor funnel.
5. Implement churn prevention programs for at-risk donors identified via inactivity windows.
6. Focus product and content investment on top-performing genres, devices, and payment methods.

**Tools & Technologies**
- Google BigQuery – Cloud data warehouse & SQL engine
- Standard SQL – Data cleaning, modelling, attribution, analytics
- CSV Outputs – BI / dashboard-ready analytical layers

**Professional Positioning**

**This project demonstrates:**
- End-to-end analytics engineering in SQL
- Analytical data modelling for business decision-making
- Marketing & customer analytics in a multi-channel environment
- Revenue attribution, segmentation, and ROI analysis
- Translation of raw data into executive-ready insights

It is designed to showcase capability for:
**Data Analyst, Business Analyst, Analytics Engineer, BI Analyst roles**

**Next Enhancements (If This Were in Production)**
- Incremental pipelines (scheduled refresh in BigQuery)
- Dashboard layer (Power BI / Looker / Tableau)
- Automated campaign performance monitoring
- Predictive churn & LTV modelling on top of this analytical base

**Author: Imaya Kehelkaduwa (Analytics & Data Engineering Portfolio)**
