# FIFA World Cup 2026 — Ticket Pricing & Stadium Fill Rate Analysis

**Does FIFA's dynamic pricing strategy maximize revenue at the cost of filling stadiums?**

## Overview

FIFA introduced dynamic ticket pricing for the first time at the 2026 World Cup, adjusting resale prices in real time based on demand. This project tracks resale ticket prices across 11 matches — ranging from high-demand host-nation games to low-demand group stage fixtures — to analyze the tradeoff between revenue maximization and stadium fill rate.

The central question: for low-demand matches, is the revenue-maximizing price the same as the price that actually fills every seat? And if not, how big is that gap, and what match characteristics predict it?

## Background

This project is grounded in a classic capacity-constrained revenue management problem — the same math behind airline seat pricing. At any positive demand curve, the revenue-maximizing price only fills a venue if marginal revenue hits zero exactly at capacity. For thin-demand matches, filling the stadium requires pricing below the revenue-maximizing point, down to wherever quantity demanded equals capacity. FIFA's dynamic pricing system, designed to maximize revenue, may be solving for the wrong objective on low-demand games — leaving visible empty sections on a global broadcast and creating a real cost for sponsors.

## Data Collection

**Source:** TheGreatReviewer FIFA World Cup 2026 Ticket Tracker (official FIFA resale marketplace data)

**Metrics recorded per observation:**
- Minimum resale price
- Median resale price
- Total listings count

**Observation frequency:** Twice a day from June 21, 2026 through each match's kickoff date

**Games tracked (11 total):**

| Game | Round | Demand Tier |
|---|---|---|
| USA vs Turkey | Group Stage | High — host nation |
| Japan vs Sweden | Group Stage | Medium |
| Curacao vs Ivory Coast | Group Stage | Low |
| France vs Norway | Group Stage | High — top-ranked team |
| Cape Verde vs Saudi Arabia | Group Stage | Low |
| Spain vs Uruguay | Group Stage | High — #1 ranked team |
| Mexico vs 3CEFHI (Ecuador) | Round of 32 | High — host nation |
| USA vs 3BEFIJ (Bosnia) | Round of 32 | High — host nation |
| 1B (Switzerland) vs 3EFGIJ (Algeria) | Round of 32 | Low — unknown teams |
| Argentina vs 2H (Cape Verde) | Round of 32 | High — defending champion |
| Winner 101 vs Winner 102 | Final | Speculative |

## Planned Analysis

**Price decay curves** — For each game, plot median and minimum price against days until kickoff. High-demand games should hold price and sell through; low-demand games should show steady decay toward FIFA's $60 supporter tier floor.

**Fill rate regression** — Using official post-match attendance figures, regress fill rate against combined FIFA ranking, host nation dummy, stadium capacity, and round to identify which factors predict a game being at risk of visible empty sections.

**Revenue vs fill rate tradeoff** — For each game, estimate the gap between the revenue-maximizing price (where price held steady while demand was active) and the market-clearing price (what it actually took to fill the seats). Quantify this gap across the demand spectrum and frame a concrete recommendation for FIFA's pricing algorithm.

## Repository Structure

```
worldcup-ticket-pricing/
│
├── worldcup_data_collection.xlsx   # Raw data collection workbook (2 tabs)
├── raw_data.csv                    # Exported price observations (added post-collection)
├── game_index.csv                  # Exported game metadata + attendance (added post-collection)
├── worldcup_analysis.ipynb         # Python analysis notebook (added post-collection)
└── README.md
```

## Tools

- **Data collection:** Microsoft Excel (online)
- **Version control:** GitHub
- **Analysis:** Python (pandas, matplotlib, statsmodels)

## About

Created by Jack Middleton — rising junior at UC Santa Barbara studying Statistics & Data Science and Economics, and a Division I soccer player. Built as a portfolio project demonstrating applied sports analytics, economic reasoning, and data collection methodology.

*Data collection in progress — analysis and findings to be added upon completion.*
