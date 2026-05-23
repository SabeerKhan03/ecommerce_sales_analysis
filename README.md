Google Merchandise Store Ecommerce Analysis

## Overview

Analyzed real Google Analytics session data from the Google Merchandise Store using BigQuery SQL. 
The goal was to answer key business questions about revenue, traffic quality, product performance, and customer behaviour — the same questions a data analyst would face in a real ecommerce role.

---



## Tools & Dataset

| Item | Detail |

| Tool | Google BigQuery |
| Dataset 1 | `bigquery-public-data.google_analytics_sample.ga_sessions_20170801` |
| Dataset 2 | `data-to-insights.ecommerce.all_sessions` |
| Data | Real Google Analytics data — August 1, 2017 |

---

=====================================================

## Business Questions Answered

| # | Question | Query |


| 1 | Which cities generated the highest total revenue? | [Query 1](#query-1-top-cities-by-revenue) |

| 2 | Which traffic source brings in the most revenue? | [Query 2](#query-2-traffic-source-analysis) |

| 3 | What percentage of sessions resulted in a purchase? | [Query 3](#query-3-overall-conversion-rate) |

| 4 | Which traffic channel has the highest conversion rate? | [Query 4](#query-4-conversion-rate-by-traffic-source) |

| 5 | How do cities rank within their own country by revenue? | [Query 5](#query-5-city-revenue-ranking-within-each-country) |

| 6 | What are the top 10 products by units sold? | [Query 6](#query-6-top-10-products-by-units-sold) |

| 7 | Which visitors added to cart but never purchased? | [Query 7](#query-7-cart-abandonment-analysis) |

| 8 | Which high-volume traffic sources convert above 1%? | [Query 8](#query-8-conversion-rate-cte-version) |

---


========================================================

## Key Findings

### 1. Revenue is concentrated in US cities
San Francisco ($2,964), New York ($1,659), and Chicago ($1,158) account for the majority of all revenue on this day. 
All meaningful purchases originated from the United States.

### 2. Direct traffic is the only converting channel
Out of all traffic sources with more than 50 sessions, only direct traffic achieved a conversion rate above 1% (1.94%). 
YouTube sent 180 visitors and generated zero purchases. Partners sent 52 visitors with zero purchases. 
This suggests a significant gap between brand awareness channels and actual revenue generation.

### 3. Overall conversion rate is 1.68%
43 purchases from 2,556 total sessions. 
This falls within the typical ecommerce industry benchmark of 1–3%, but leaves clear room for improvement — particularly given the poor performance of non-direct channels.

### 4. Google and YouTube apparel dominates product views
The Google Men's Cotton T-Shirt had 338,436 session appearances — nearly 50% more than the second place product. 
All top 10 products are branded apparel, suggesting the store's audience is strongly brand-loyal.

### 5. Cart abandonment is a recoverable revenue opportunity
Identified a list of visitor IDs who added items to cart but never completed checkout. 
In a production environment this list would feed a retargeting email campaign to recover lost revenue.

---

=======================================================

## SQL Concepts Demonstrated

| Concept | Used In |

| Aggregations — COUNT, SUM | Queries 1, 2, 3, 6 |
| GROUP BY, ORDER BY, LIMIT | Queries 1, 2, 4, 6 |
| HAVING — filtering after grouping | Queries 4, 7 |
| NULL handling | Queries 1, 2, 3 |
| Window Functions — RANK(), PARTITION BY | Query 5 |
| CASE WHEN — conditional logic | Query 7 |
| CTEs — Common Table Expressions | Query 8 |
| Funnel analysis logic | Query 7 |
| Nested column access (BigQuery) | Queries 1–5 |




## How to Run These Queries

1. Go to [console.cloud.google.com/bigquery](https://console.cloud.google.com/bigquery)
2. Create a free Google Cloud account (1TB free queries/month)
3. Open the query editor
4. Copy any query from `queries.sql` and click Run
5. No dataset setup needed — both datasets are publicly available



## Folder Structure

```
project1_ecommerce_analysis/
│
├── sql_queries.sql        # All 8 SQL queries with detailed comments
└── README.md              # This file — findings and documentation
```

---

## Skills Demonstrated

`BigQuery` `SQL` `Google Analytics Data` `Funnel Analysis` `Conversion Rate Analysis` `Window Functions` `CTEs` `CASE WHEN` `Ecommerce Analytics` `Business Intelligence`
