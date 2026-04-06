# Cyclistic-Cyclist-Behavior-Analysis-and-Optimization

> End-to-end analysis of 1M+ bike-share trips across Chicago to identify behavioral
> differences between casual riders and annual members, and recommend data-driven
> conversion strategies.

**Published tools:** `SQL` `R` `R Markdown` `Tableau` `PowerPoint`

---

## Background

About the company
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are tracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system at a time.

Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. 
Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.
Cyclistic’s finance analysts have concluded that **annual members are much more profitable than casual riders**. 
Although the pricing flexibility helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. 
Rather than creating a marketing campaign targeting all-new customers, Moreno believes there is a good chance to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.

**Moreno has set a clear goal**: Design marketing strategies aimed at converting casual riders into annual members. 
In order to do that, however, the marketing analyst team needs to understand better how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

---

## Dataset

- **Source:** [Divvy Trip Data](https://divvytripdata.s3.amazonaws.com/index.html) — publicly available under Motivate International Inc. license
  (Note: The datasets have a different name because Cyclistic is a fictional company. Motivate International Inc. has made the data available under this license.) 
This is public data you can use to explore how different customer types use Cyclistic bikes. But note that data privacy issues prohibit you from using riders’ personally identifiable information. This means that you won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.
- **Period:** 2021 – 2022 (24 months)
- **Size:** 1M+ records · 13 features
- **Features:** Ride ID, Bike Type, Start/End Time, Start/End Station, Start/End Coordinates, Rider Type (casual/member)

---

## Pipeline

| Step | Tool | What Was Done |
|------|------|---------------|
| 1 | **SQL (PostgreSQL)** | Loaded 11 monthly CSVs into individual tables, merged into a single master table (`Cyclistic_2022`) using `UNION ALL`, exported as CSV |
| 2 | **R** | Data wrangling — removed NAs, filtered negative ride durations/distances, parsed dates, engineered `ride_duration` (difftime), `ride_length` (Haversine distance), `season`, `weekday`, `month` |
| 3 | **R (ggplot2)** | Initial visualizations — member vs casual split, bike preference, weekly riding patterns |
| 4 | **R Markdown** | Documented full analysis pipeline with embedded code and outputs as a reproducible PDF report |
| 5 | **Tableau** | Deep-dive on top 30 riders by duration — station-level maps, weekly/monthly/seasonal trends, casual vs member comparisons |
| 6 | **PowerPoint** | Summarized Tableau findings into a stakeholder-facing presentation |

---

## Key Findings

| # | Finding | Detail |
|---|---------|--------|
| 1 | **Usage pattern** | Members ride consistently throughout the week (commuting); casual riders peak on weekends (recreation) |
| 2 | **Ride duration** | Casual riders take longer trips than members on average |
| 3 | **Ride distance** | Casual riders cover greater distances; average distance declined in 2022 vs 2021 |
| 4 | **Seasonality** | Both groups peak in summer; casual rider activity decreased from 2021 to 2022 while member usage remained stable |
| 5 | **Location** | Casual riders cluster downtown and near Millennium Park; members are spread evenly across the city |
| 6 | **Bike preference** | Classic bikes are preferred by both groups; docked bikes are almost entirely unused |
| 7 | **Membership trend** | Casual rider count increased from 2021 to 2022, representing a conversion opportunity |

---

## Conclusions

1. **Members are commuters, casual riders are tourists/recreational users** — the behavioral split is clear and consistent across both years.
2. **Casual riders are high-value targets** — they already use the service and ride longer, but have not committed to membership.
3. **Summer is the highest-leverage conversion window** — casual activity peaks mid-year, making it the optimal time for membership campaigns.
4. **Downtown and Millennium Park are key acquisition locations** — casual riders concentrate here, making them ideal for on-site and geo-targeted promotions.
5. **Docked bikes are operationally wasteful** — negligible usage across both user types and both years.

---

## Recommendations

| Priority | Area | Recommendation |
|----------|------|----------------|
| 🔴 High | Conversion campaign | Run summer membership promotions targeting casual riders — peak activity window with highest conversion potential |
| 🔴 High | Location targeting | Focus marketing at downtown stations and Millennium Park where casual riders concentrate |
| 🟡 Medium | Weekend promotions | Highlight commuting benefits of membership to weekend casual riders at high-traffic stations |
| 🟡 Medium | Member retention | Survey members to investigate the drop in average ride duration in 2022 — identify and address churn risk |
| 🟢 Low | Fleet optimization | Retire or reassign docked bikes — near-zero usage across all segments reduces fleet efficiency |

---

## Repository Structure

```
├── Github_file_Cyclists.sql                        # SQL — master dataset creation
├── Cyclist-Behavior-Analysis-and-Optimization.R    # R — data wrangling and ggplot visualizations
├── Cyclists_R_Markdown.pdf                         # R Markdown — reproducible analysis report
├── Tableau Analysis of Casual vs Member Riders.pdf # Tableau — exported dashboard insights
├── Tableau Analysis of Casual vs Member Riders.pptx# PowerPoint — stakeholder presentation
├── Book4.twb                                       # Tableau workbook
└── README.md
```

---

## Stack

`SQL (PostgreSQL)` `R` `tidyverse` `ggplot2` `lubridate` `geosphere` `R Markdown` `Tableau` `PowerPoint`
