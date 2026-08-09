An interactive Power BI dashboard analyzing Airbnb listing performance, host trust signals, guest ratings, and review activity across **10 major global cities**.

---

## 📌 Overview

This dashboard explores Airbnb's global footprint through three lenses: overall market growth, guest satisfaction ratings, and reviewer/trust behavior. It combines a 279K-listing dataset spanning 2008–2020 with host verification and review-frequency data to surface actionable, data-backed insights rather than just raw charts.

**Key metrics tracked:** 2,79,712 listings · 10 cities · 1,82,024 hosts · 144 property types · 5,373K reviews

---

## 🖼️ Dashboard Pages

### 1. Overview
Tracks Airbnb's total listing growth from 2008–2020 across an "Introduction → Growth → Maturity → Decline → Reinvention → COVID-19" market lifecycle, broken out by room type (Entire Place, Private Room, Shared Room, Hotel Room).

> *In 2015, Airbnb reached the highest number of new listings. 2016 and 2017 saw a restraint due to a tightening in local regulations. Despite this, Airbnb became profitable in the second half of 2016, and 2017 marked the first full year of generating income. From 2018, growth resumed until it was stopped in 2019 by the COVID-19 pandemic.*

### 2. Ratings
A Pareto (cumulative %) breakdown of market share by city, average nightly price by room type, and a city-by-metric ratings heatmap (Accuracy, Cleanliness, Communication, Location, Value), with a toggle between overall and detailed rating views.

> *Paris, NYC, and Sydney account for almost half of the total listings and 48% of total reviews. Paris is the city with the most listings and reviews — a possible driver is hotel room prices being roughly twice as much as Airbnb.*
>
> *Mexico City and Rio are the overall best-rated cities; Hong Kong and Istanbul the worst. Cleanliness and value-for-money are the two metrics that generally score lowest.*

### 3. Reviews
Covers reviewer frequency distribution, seasonal review share by city across the year, and a host "Trust" shield showing the split between identity-verified/unverified hosts with and without profile pictures.

> *Most customers wrote a review only once — 98.8% did so 3 times or less. One customer wrote 283 reviews, the last two on the same day across two listings in Bangkok (data error, or a genuine super-reviewer).*
>
> *Paris and Rome dominate review share from April to August, reflecting peak European summer travel; New York sees an uptick in November and December during the holiday season.*
>
> *Over two-thirds of Airbnb hosts are fully identity-verified, while nearly all hosts provide at least one trust signal (verification or profile picture), keeping fully anonymous, unverified profiles to a minimum.*

---

## 🛠️ Tech Stack

- **Power BI Desktop** — report authoring and data modeling
- **Power Query (M)** — data cleaning, staging queries, and fiscal/date logic
- **DAX** — 25+ custom measures and calculated columns (cumulative distributions, Pareto %, host-verification segmentation, rating aggregates)
- **Data Modeling** — star-schema relationships between `Listings` and `Reviews` fact/dimension tables, with a dedicated Date table for time intelligence

## 📊 Data Source

**Source:** [Maven Analytics Data Playground — Airbnb Listings & Reviews](https://mavenanalytics.io/data-playground/airbnb-listings-reviews)

The dataset contains listing-level and review-level records for Airbnb properties across 10 global cities (Bangkok, Cape Town, Hong Kong, Istanbul, Mexico City, New York, Paris, Rio de Janeiro, Rome, and Sydney), including host verification status, property/room type, pricing, guest ratings by category, and individual review timestamps spanning 2008–2020.

## 🗂️ Data Model

| Table | Purpose |
|---|---|
| `Listings` | Core listing + host attributes: host verification status, profile picture flag, response rate/time, superhost status, property/room type, location |
| `Reviews` | Review-level records: reviewer ID, review date, per-reviewer frequency, monthly review share |
| `Date` | Standard calendar table powering all time-based visuals |

## 📁 File Format

- `.pbix` — full working file with data (open in Power BI Desktop)
- `.pbit` — template version (structure and visuals only, no embedded data)

## 🎯 Business Problem

Airbnb operates across hundreds of cities with wildly different market dynamics, host behaviors, and guest expectations. Without a consolidated view, it's difficult for analysts, city managers, or trust & safety teams to answer basic questions like: which cities dominate the market, where is guest satisfaction weakest, and how trustworthy is the host base — all at a glance.

## 🎯 Goal of the Dashboard

Give stakeholders a single, interactive view to:
- Track overall marketplace growth and how room-type mix has shifted over time
- Identify which cities drive the most listings, reviews, and revenue share
- Spot where guest satisfaction (cleanliness, value, communication) is weakest
- Quantify how much of the host base is identity-verified and trustworthy
- Understand seasonal review patterns to anticipate demand cycles

## 🚶 Walkthrough of Key Visuals

- **New Listings (Overview):** an area chart mapped against Airbnb's market lifecycle stages (Introduction → Growth → Maturity → Decline → Reinvention → COVID-19), split by room type
- **Market Share by City (Ratings):** a Pareto chart showing cumulative % of listings/reviews contributed by each city, revealing that just 3 cities account for nearly half the market
- **Ratings Heatmap (Ratings):** city-by-metric conditional-formatted table across Accuracy, Cleanliness, Communication, Location, and Value
- **Review Frequency (Reviews):** a cumulative distribution showing how concentrated reviewing behavior is among a small set of repeat reviewers
- **Trust Shield (Reviews):** a 2×2 breakdown of hosts by identity verification × profile picture presence
- **Seasonality Ribbon (Reviews):** month-by-month review share per city, exposing peak-season shifts

## 💡 Business Impact & Insights

- **Marketing optimization:** Airbnb (or a competing platform) could focus city-specific campaigns on the 3 cities driving ~48% of reviews, or specifically target underperforming-rating cities like Hong Kong and Istanbul with host-improvement programs.
- **Trust & Safety:** with over two-thirds of hosts fully verified, remaining unverified/no-profile-picture hosts (a small but real segment) can be flagged for targeted verification outreach.
- **Seasonal demand planning:** knowing Paris and Rome peak April–August while New York peaks in Nov–Dec allows better inventory/pricing strategy timing per city.
- **Pricing strategy:** hotel rooms averaging ~2x the price of an Airbnb entire-place listing highlights Airbnb's core value proposition and a lever for competitive positioning.

## 📷 Screenshots

### Overview
![Airbnb Overview](Airbnb%20Overview.png)

### Ratings
![Airbnb Ratings](airbnb%20%20ratings.png)

### Reviews
![Airbnb Reviews](airbnb%20reviews.png)

---

## 📥 Download

- [Download the Power BI Template (.pbit)](https://github.com/Prerak7999/airbnb-performance-dashboard/blob/main/airbnnb%20project%20template.pbit)

