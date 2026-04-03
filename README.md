<div align="center">
  <img src="logos/Logo_Emerson.svg.png" alt="Emerson logo" width="220" />
</div>

<h1 align="center">National Data Challenge 2025 Participant Project | Manufacturing Downtime Analysis</h1>

<p align="center">
  A competition portfolio project built for the National Data Challenge 2025, focused on production efficiency,
  downtime drivers, operator performance, and product-level bottlenecks in a soda bottling line.
</p>

## Client Background

This repository contains my participant submission work for the **National Data Challenge 2025**, using a manufacturing downtime case provided through the **Maven Data Playground**. The scenario focuses on a soda bottling production line where management needs a clear view of how downtime is affecting line efficiency, daily output, and operational performance.

The dataset combines batch-level production records, product metadata, and downtime causes. The objective is to identify where production time is being lost, determine which issues are preventable, and provide recommendations that improve throughput and reduce avoidable downtime.

## Business Problem

Production teams need to answer four operational questions:

1. How efficiently is the line running relative to ideal production time?
2. Which downtime factors are driving the biggest losses?
3. Which products and operators are associated with the most downtime?
4. What actions should leadership prioritize to recover productive time?

## Northstar Metrics

- `Line efficiency (%)`
- `Total downtime (minutes)`
- `Average downtime per production day`
- `Total batches produced`
- `Preventable vs non-preventable downtime share`
- `Downtime by factor, product, date, and operator`

## Executive Summary

This analysis covers **38 batches** produced across a short operating window in late August to early September 2024. Across those batches, the line accumulated **1,388 minutes of downtime**, pushing total production time to **3,858 minutes** against an ideal baseline of **2,470 minutes**. That translates to an overall **line efficiency of 64.02%**.

The strongest signal in the data is that downtime is not concentrated in one isolated issue. Instead, the biggest losses are spread across equipment-related interruptions and process execution problems. **Machine adjustment (332 mins)**, **machine failure (254 mins)**, and **inventory shortage (225 mins)** are the three largest contributors. At the same time, **55.91%** of all downtime is linked to operator-related or otherwise preventable causes, indicating that process discipline and standardization matter almost as much as equipment reliability.

At the product level, **CO-600** accounts for the highest downtime at **494 minutes**, followed by **CO-2L (277 mins)** and **RB-600 (258 mins)**. At the operator level, **Charlie (384 mins)** and **Dee (370 mins)** carry the highest downtime totals. These patterns point to a need for targeted corrective action rather than broad, generic process changes.

## Dashboard Preview

<div align="center">
  <img src="ManufacturingDowntimeAnalysis/ManufacturingDowntimeAnalysis_00.png" alt="Manufacturing Downtime Analysis dashboard" width="1100" />
</div>

## Dataset Structure

The workbook includes four related tables:

1. `Line productivity`
   Batch-level production records with date, product, operator, start time, and end time.
2. `Products`
   Product dimension containing flavor, size, and minimum batch time.
3. `Downtime factors`
   Downtime reason lookup with descriptions and operator-error flags.
4. `Line downtime`
   Batch-level downtime minutes broken out by factor.

## Data Snapshot

- `38` batches produced
- `6` products in scope
- `4` operators in scope
- `11` tracked downtime factors with recorded downtime
- `5` production dates with activity in the source data

## Insights Deep-Dive

### 1. Overall Efficiency

- The production line operated at **64.02% efficiency**.
- The line spent **1,388 excess minutes** above ideal production time, which exactly matches the recorded downtime total.
- Average downtime was **277.6 minutes per active production day**, showing that downtime was material, not incidental.

### 2. Downtime Drivers

- **Machine adjustment** was the largest downtime factor at **332 minutes**.
- **Machine failure** followed with **254 minutes**, reinforcing that equipment stability is a major issue.
- **Inventory shortage** added **225 minutes**, indicating downtime is also driven by upstream planning and material availability.
- **Batch change (160 mins)** and **batch coding error (145 mins)** show that changeover and execution quality are significant contributors.

### 3. Preventable vs Non-Preventable Downtime

- **55.91%** of downtime was tied to operator-related or preventable causes.
- **44.09%** was non-preventable based on the source classification.
- This split suggests the business can recover a meaningful amount of time through training, SOP tightening, and better shift execution without waiting solely on capital or maintenance fixes.

### 4. Product Performance

- **CO-600** generated the highest downtime at **494 minutes**, making it the biggest bottleneck product in the dataset.
- **CO-2L** contributed **277 minutes**, while **RB-600** contributed **258 minutes**.
- **OR-600** recorded the lowest downtime at **75 minutes**, though it also appeared in only one batch, so it should not be treated as proof of stable performance.
- Batch volume matters here: **CO-600** also had the highest production count with **15 batches**, so its downtime should be evaluated both as a total-loss issue and as a high-frequency product control problem.

### 5. Operator Findings

- **Charlie** recorded the highest total downtime at **384 minutes**.
- **Dee** followed closely at **370 minutes**.
- **Mac** and **Dennis** recorded **332 minutes** and **302 minutes**, respectively.
- Since downtime is relatively concentrated across all four operators, this looks less like a single-person issue and more like a process consistency problem with targeted coaching opportunities.

### 6. Daily Downtime Story

- **September 2, 2024** was the worst day with **503 minutes** of downtime.
- **August 30, 2024** was the second-worst day at **444 minutes**.
- **September 3, 2024** was the lightest active day at **32 minutes**.
- The volatility across days suggests downtime events cluster around specific operating conditions rather than occurring at a flat, predictable rate.

## Recommendations

### Operations

- Prioritize root-cause analysis for **machine adjustment** and **machine failure**, since those two factors alone account for **586 minutes**, or more than two-fifths of total downtime.
- Introduce a daily downtime review for high-loss days to isolate repeatable triggers behind the spikes on **August 30, 2024** and **September 2, 2024**.
- Track downtime against ideal batch time as a standing production KPI so teams can measure recovered minutes, not just incident counts.

### Process Improvement

- Tighten batch change and batch coding procedures, since those two process issues contributed **305 minutes** combined.
- Standardize pre-run checks for materials and line readiness to reduce **inventory shortage** delays before production starts.
- Build a short escalation workflow for recurring downtime factors so common issues are resolved faster during the shift.

### People and Training

- Focus training on the preventable side of downtime first, because **55.91%** of all lost time is theoretically recoverable through better execution.
- Review operator-specific patterns for **Charlie** and **Dee**, then compare them against shift assignments, product mix, and downtime types before deciding on interventions.
- Reinforce operating standards during changeovers, coding steps, and line adjustments, where a large share of avoidable losses appears to occur.

### Product and Planning

- Audit the **CO-600** production flow first, since it carries both the highest batch volume and the highest downtime total.
- Review whether **CO-2L** and **RB-600** require different setup, material handling, or maintenance preparation than lower-downtime products.
- Pair downtime analysis with scheduling decisions so product runs with known friction points receive stronger staffing, staging, or maintenance support.

## Tools Used

- `Power BI` for dashboard design and analysis
- `Excel` for source data
- `PDF` export for presentation-ready reporting

## Repository Contents

- [`ManufacturingDowntimeAnalysis.pbix`](ManufacturingDowntimeAnalysis.pbix) - Power BI source file
- [`ManufacturingDowntimeAnalysis.pdf`](ManufacturingDowntimeAnalysis.pdf) - exported dashboard/report
- [`National Data Challenge 2025.pdf`](National%20Data%20Challenge%202025.pdf) - challenge/project document
- [`dataset/National Data Challenge 2025 - Manufacturing Downtime/Manufacturing_Line_Productivity.xlsx`](dataset/National%20Data%20Challenge%202025%20-%20Manufacturing%20Downtime/Manufacturing_Line_Productivity.xlsx) - source dataset
- [`dataset/National Data Challenge 2025 - Manufacturing Downtime/data_dictionary.csv`](dataset/National%20Data%20Challenge%202025%20-%20Manufacturing%20Downtime/data_dictionary.csv) - data dictionary

## Outcome

This repository is positioned as a competition analytics portfolio project that moves from business context to executive summary, insight deep-dive, and recommendations. The structure is intentionally designed to present my National Data Challenge 2025 participant work as a stakeholder-facing case study rather than only a file dump.
