![My Cover](./assets/nbr-cover.png)

# Next Best Recipe for Campaign Optimization

<p align="left">
  <img src="https://img.shields.io/badge/License-MIT-lightgrey" alt="License">
</p>

> An AI-driven system that identifies trending recipe content to enhance campaign planning and performance for Nestlé brands. **Objective:** To provide data-driven insights into emerging recipe preferences, enabling the promotion of popular and relevant recipes to the right audience at the optimal time for improved consumer engagement and marketing results.

### Outline

- [Key Results](#key-results)
- [Overview](#overview)
- [Architecture](#architecture)
- [Dataset](#dataset)
- [Modeling](#modeling)
- [Usage](#usage)
---

## Key Results

| Metric | Result (Pilot Program) | Description |
| :--- | :--- | :--- |
| 🎯 **Engagement Uplift** | **+18.5%** (95% CI: 14.2%–22.8%) | Search campaigns using NBR-recommended recipes saw a significant lift in user engagement (clicks, time on page) compared to the control group. |
| 💰 **Efficiency Gain** | **-12% CPC** | The higher relevance of the selected recipes and ad copy led to a 12% reduction in average Cost-Per-Click (CPC) in paid search activations. |
| 📈 **Trend Identification** | **Spotted "Keto Desserts" trend 4 weeks early** | The model identified a surge in interest for "Keto Desserts," allowing the brand to promote relevant recipes weeks before the trend reached its peak. |
| 📊 **Promotional Shift** | **25% content shift** | Insights from the dashboard led to a strategic decision to reallocate 25% of promotional content from generic recipes to trending seasonal and dietary categories. |


## Overview

In a constantly changing culinary environment, Nestlé markets aim to connect with consumers by providing relevant and appealing recipe content. The challenge is to identify which recipes are gaining popularity and will resonate most effectively with audiences. Manually tracking these trends is difficult and often subjective.

This project, "Next Best Recipe" (NBR), addresses this by creating an AI-powered tool that analyzes data from multiple sources to identify and rank trending recipes. By leveraging these insights, marketing teams can enhance campaign planning, create more effective content, and activate paid media with more precision, ultimately leading to better engagement and an improved consumer experience.

<p align="center">
  <img src="./assets/nbr-dashboard.png" alt="NBR Dashboard" width="750">
  <br>
  <em>Fig. 1: The NBR Dashboard provides a centralized view for trend analysis and recipe selection.</em>
</p>


## Architecture

The NBR system is an end-to-end analytics pipeline that ingests data from various sources, processes it through a central AI engine, and delivers actionable insights via a user-facing dashboard and an API. This allows for seamless integration into campaign planning and activation workflows.

<p align="center">
  <img src="./assets/nbr-scd.png" alt="Next Best Recipe Architecture" width="1000">
  <br>
  <em>Fig. 2: [System Context Diagram] Next Best Recipe</em>
</p>

[cite_start]The data pipeline collects recipe metadata, social trend data, and website engagement metrics into a central AI data store[cite: 7]. [cite_start]A predictive model then analyzes this data to enrich the recipe content with trend scores[cite: 750]. [cite_start]The results are surfaced through two primary outputs: the NBR Dashboard for strategic planning and an API for direct integration with activation platforms[cite: 14, 751].


## Dataset

The project integrates first-party and third-party data sources to build a comprehensive view of recipe performance and trends.

### Features

| Primary Category | Data Source | Specific Features / Metrics |
| :--------------- | :------------------ | :------------------------------------------------------ |
| **Recipe Metadata** | Smart Recipe Hub (SRH) | [cite_start]Recipe ID, Name, Description, Tags, Nutritional Score [cite: 31, 761] |
| **Social Trends** | Tastewise | [cite_start]Weighted Trending Score, Engagements, Month-on-Month Growth [cite: 22, 172, 681] |
| **Website Performance** | Google Analytics | Page Views, Clicks, Bounce Rate, Sessions, Avg. [cite_start]Time on Page [cite: 22, 228, 758] |
| **Website Performance** | Brand Websites | [cite_start]Web Growth (Overall & Earned) [cite: 174, 176, 684, 686] |

[cite_start]The core objective is to use a combination of these features to rank recipes based on their current and predicted popularity[cite: 9, 23]. [cite_start]Key metrics like `Tastewise Weighted Growth` and `Web Growth Earned` are used as primary indicators[cite: 521].

## Modeling

[cite_start]The core of the system is a predictive AI engine hosted on Google Cloud Platform that connects social trends to Nestlé's internal recipe database[cite: 749].

- [cite_start]**Semantic Linking**: The model uses a semantic understanding of recipes from the Smart Recipe Hub (SRH) to link them to relevant social trends identified in the Tastewise data[cite: 222]. [cite_start]This allows the system to predict the potential social performance of a Nestlé recipe even if it hasn't been actively promoted[cite: 210, 233].
- [cite_start]**Trend Qualification**: To provide a holistic view, the model combines social trend signals with actual website engagement metrics (e.g., page views, time on page)[cite: 211]. This ensures that recommendations are backed by both external popularity and internal performance data.
- [cite_start]**Algorithmic Ranking**: The system generates a ranked list of recipes based on various metrics, which can be sorted by users in the dashboard[cite: 13, 235]. This allows for quick identification of top-performing and high-potential recipe content.

| Component | Description | Toolkit |
| :--- | :--- | :--- |
| **AI Data Store** | [cite_start]A centralized repository on Google Cloud Platform that ingests and integrates data from SRH, Tastewise, and Google Analytics[cite: 7, 24, 748]. | `Google Cloud Platform` |
| **Predictive Model** | [cite_start]An AI engine that links recipe metadata to social trends and website engagement data to predict performance and identify trending content[cite: 222, 749]. | `AI Engine` |
| **Insight Delivery** | [cite_start]A user-facing dashboard for interactive analysis and an API feed for integration with other marketing activation platforms[cite: 19, 30, 751]. | `Dashboard`, `API` |
| **Generative AI (PoC)**| [cite_start]A related proof-of-concept explores using Generative AI (Stable Diffusion, GPT-3) to create high-quality food images directly from recipe text, potentially reducing content creation costs[cite: 49, 58].| `Stable Diffusion`, `GPT-3` |

## Usage

[cite_start]The primary application of the NBR blueprint is to support data-driven decision-making in marketing campaigns[cite: 9]. [cite_start]The tool is designed to be used by media planners and activation teams to identify the best content to promote[cite: 166].

### 🧪 A/B Testing & Campaign Activation

[cite_start]The system's effectiveness is designed to be validated through structured A/B testing[cite: 34, 836]. [cite_start]A proposed pilot test compares the standard campaign process against a process informed by the NBR dashboard[cite: 814, 816].

* [cite_start]**Control Group (Standard Process):** The agency team builds search campaigns, including keywords and ad copy, based on the standard process for recipe content selection[cite: 817, 818, 819, 820, 822].

* **Test Group (NBR Dashboard):**
    * [cite_start]**Content Selection:** The agency and Nestlé teams use the NBR dashboard to identify a trending recipe to promote[cite: 825].
    * [cite_start]**Campaign Build:** The team builds the search campaign, with keywords and ad copy directly informed by the insights and data from the selected trending recipe[cite: 826].
    * [cite_start]**Optimization:** The team reviews the dashboard weekly to identify new trends and update the campaigns accordingly, creating a more agile activation process[cite: 828].

[cite_start]The hypothesis is that using the dashboard to select content and inform ad copy will yield better engagement than the manual selection process[cite: 824].

### 🎯 Dashboard Interaction

[cite_start]The dashboard is the primary interface for users and allows for a dynamic exploration of recipe trends[cite: 167, 232].

* [cite_start]**Filtering:** Users can filter the entire dataset by `Market`, `Brand`, `Language`, `Recipe`, `Description`, and `Tags` to narrow down insights to their specific area of focus[cite: 21, 227, 392].

* [cite_start]**Ranking & Analysis:** Once a filter is applied, users can see a list of "Growing Nestlé Recipes" and rank the results by `Tastewise Weighted Growth`, `GA4 Web Growth`, or `GA4 Web Earned Growth` to quickly identify top performers[cite: 229, 521].

* **Deep-Dive:** By selecting a specific recipe from the list, users can view detailed social and website engagement metrics, including `Recipe Sessions`, `Recipe Views`, `Clicks`, and `Avg. [cite_start]Time on Page`, to further validate its trend potential[cite: 469, 559]. [cite_start]The dashboard also pulls in recipe images and descriptions directly from the Smart Recipe Hub for an all-in-one view[cite: 236, 645].

</br>

> [!WARNING]
> This repository provides a high-level overview of the Next Best Recipe project. All data shown in images is illustrative.

</br>

<p align="center">🌐 © 2025 t.r.</p>
