# NovaTech Revenue Intelligence Dashboard

Agentic BI project built with **Amazon Quick**, combining multi-source data ingestion, transformation, dashboard design, and natural-language (NL) query configuration to answer real business questions across marketing, sales CRM , and customer support data.

## Overview
[NovaTech_README.md](https://github.com/user-attachments/files/32708352/NovaTech_README.md)

[novatech_support_tickets.csv](https://github.com/user-attachments/files/32708328/novatech_support_tickets.csv)

[novatech_marketing_campaigns.csv](https://github.com/user-attachments/files/32708326/novatech_marketing_campaigns.csv)

[novatech_crm_deals.csv](https://github.com/user-attachments/files/32708325/novatech_crm_deals.csv)


This project simulates a full business intelligence workflow for a fictional company, **NovaTech**, using Amazon Quick's agentic AI capabilities to go from raw CSV data to a fully interactive, NL-queryable BI dashboard. The goal was to build a dashboard that a non-technical stakeholder could question in plain English and get accurate, trustworthy answers from — not just a set of static charts.

## Datasets

Four datasets were ingested and joined into a unified analytical model:

| Dataset | Records | Columns | Domain |
|---|---|---|---|
| `novatech_crm_deals.csv` | 499 | 20 | Sales pipeline, deal stages, revenue |
| `novatech_marketing_campaigns.csv` | 2,240 | 20 | Campaign performance, funnel stages |
| `novatech_support_tickets.csv` | 3,000 | 20 | Customer support tickets, sentiment |
| `novatech_fourth_dataset.csv` | — | — | Joined output of the three datasets above |

## Process

### 1. Data Verification & Preparation
- Verified pre-indexed knowledge bases and confirmed row/column counts for each dataset
- Audited column naming conventions across all three source datasets, flagging inconsistencies (e.g., an ambiguous `Mkt_Src_Cd` column later renamed to `market_source_code`) and confirming null-value counts per column
- Corrected data types (dates, integers, decimals) and renamed unclear columns (e.g., `list_price` → `list_price_usd`, `deal_value` → `deal_revenue_usd`) for analysis-readiness
- Added calculated columns, including `days_to_close`, `resolution_time`, and `campaign_ROI`, to support downstream analysis

### 2. Data Modeling
- Joined the three source datasets on `account_id` using a **left join** strategy, keeping `novatech_crm_deals.csv` as the primary table
- Documented the trade-off of this approach: left joins preserve every deal record but can cause row multiplication when a right-hand table has multiple matches per key — a deliberate, documented modeling decision rather than an oversight

### 3. Dashboard Build
Built a three-sheet interactive dashboard:
- **Marketing Funnel Sheet** — campaign performance, funnel stage progression, and revenue by channel and customer segment, with filters for campaign channel and customer tier
- **Sales Pipeline Sheet** — deal revenue by sales region, product, and deal stage, filterable by company size and customer tier
- **Customer Health Sheet** — support ticket volume, priority, and sentiment by product and region, filterable by customer tier

### 4. Natural-Language Query Configuration
- Configured a Quick **Topic** to improve natural-language question accuracy, mapping technical field names to business-friendly synonyms (e.g., "annual income" ↔ "yearly revenue", "customer tier" ↔ "client tier")
- Re-tested the same natural-language questions before and after Topic configuration to validate accuracy improvements — questions that previously failed (e.g., "which marketing campaigns are actually driving the end date of the deal?") returned correct, sourced answers afterward

## Key Business Questions Answered

Using Quick Chat's agentic Q&A over the modeled dataset, the dashboard was able to answer:

1. **Which marketing campaigns are actually driving closed deals?** — Identified Partner Referral and Direct Mail as the highest-quality channels by revenue-per-response, despite Direct Mail having the lowest volume.
2. **Are highest-value customers also filing the most support tickets?** — Found no meaningful correlation between product revenue rank and ticket volume; lower-tier products were consuming disproportionate support resources relative to the revenue they generated.
3. **What's the relationship between campaign channel and deal win rate?** — Surfaced an overall 51% win rate across the pipeline, with all lost deals recording zero partial revenue.

## Tools & Skills

**Tools:** Amazon Quick (Agentic AI Workflows), Quick Chat, Topic Configuration, SPICE, CSV data ingestion

**Skills demonstrated:** Multi-source data validation, data modeling & join strategy, dashboard design, natural-language query tuning, agentic AI-assisted business analysis, data quality auditing

## Screenshots
<img width="930" height="389" alt="image" src="https://github.com/user-attachments/assets/46e65a7f-296f-400c-b5e3-491a04fc363c" />
<img width="940" height="457" alt="image" src="https://github.com/user-attachments/assets/d1f63b7b-5a56-40c9-94e6-6c8b4e1999ac" />
<img width="940" height="431" alt="image" src="https://github.com/user-attachments/assets/6e53d0e8-1d9d-4b2b-99b2-50b45445cb88" />
<img width="940" height="429" alt="image" src="https://github.com/user-attachments/assets/e4ac0287-ae4f-481e-8bf9-0efb4d16c1f6" />
<img width="940" height="427" alt="image" src="https://github.com/user-attachments/assets/e13b2e4f-8d64-46c3-80d2-561493c1b537" />
<img width="940" height="427" alt="image" src="https://github.com/user-attachments/assets/c7882b14-dc2b-41cd-90be-e28ab2214a32" />
<img width="940" height="425" alt="image" src="https://github.com/user-attachments/assets/a0bf9272-f0ac-4813-8626-0771f26a8f80" />
<img width="940" height="425" alt="image" src="https://github.com/user-attachments/assets/b890f971-2e03-4349-b7c8-b2a316fefed0" />
<img width="940" height="432" alt="image" src="https://github.com/user-attachments/assets/a7c07fe1-df5b-4410-9eb4-5784392455c2" />
<img width="940" height="428" alt="image" src="https://github.com/user-attachments/assets/cd1d3aa6-1996-480f-ae2b-e1638ebf97cb" />
<img width="940" height="253" alt="image" src="https://github.com/user-attachments/assets/e3fea792-9077-4964-9b68-e2959a2e639f" />
<img width="940" height="428" alt="image" src="https://github.com/user-attachments/assets/9674f164-4e24-4b0d-9bdb-25149998054a" />
<img width="940" height="422" alt="image" src="https://github.com/user-attachments/assets/a386e0eb-b759-4de7-9724-13481917966a" />
<img width="940" height="428" alt="image" src="https://github.com/user-attachments/assets/63da55fd-36b3-4aba-b146-d00a0788ee4b" />
<img width="940" height="401" alt="image" src="https://github.com/user-attachments/assets/36648191-e299-4c6b-b663-eed617523b1b" />
<img width="940" height="423" alt="image" src="https://github.com/user-attachments/assets/48dc7dfe-e49f-4b04-8aef-88e55e2ff76c" />
<img width="940" height="415" alt="image" src="https://github.com/user-attachments/assets/3497426f-8341-4f5f-8bc4-5093161660c9" />
<img width="940" height="415" alt="image" src="https://github.com/user-attachments/assets/afbd37d4-7878-46bd-8498-30bacb029d42" />
<img width="940" height="417" alt="image" src="https://github.com/user-attachments/assets/e2703f71-2ce1-4059-b1b6-c6bffae5ce7b" />
<img width="940" height="411" alt="image" src="https://github.com/user-attachments/assets/a4ad68e2-9186-4ccf-a16b-2b203465e61a" />
<img width="940" height="421" alt="image" src="https://github.com/user-attachments/assets/5de4c275-70fd-4e55-883b-0fec467f3d80" />
<img width="940" height="422" alt="image" src="https://github.com/user-attachments/assets/5d04e729-cb51-4786-8f12-85cc61d90866" />
<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/1e0dba7a-c1a2-41f2-97bc-ee9fb31d4403" />
<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/d0a5bd5f-f84f-4955-a37e-5d3433fd8cd3" />

## Notes

This project was completed as a hands-on training exercise using Amazon Quick, focused on building practical, real-world BI workflow skills — from raw data to a natural-language-queryable dashboard.
