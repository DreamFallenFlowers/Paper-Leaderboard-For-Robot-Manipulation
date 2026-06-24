# Robot Manipulation Knowledge Base

A searchable, updateable, and composable leaderboard for robot manipulation papers, built to help you find the work that truly matters.

[Homepage](https://dreamfallenflowers.github.io/Paper-Leaderboard-For-Robot-Manipulation/) · [中文 README](./README.zh-CN.md)

## Quick Facts

- Tracks robot manipulation papers on arXiv from **2023-01-01** to the latest project update
- Covers **11038** papers
- Includes **76** keywords
- Supports **three ranking modes**: `Overall`, `Hot`, and `Newest`
- Updated **monthly**
- The full workflow will be open-sourced within **one week**

## Why This Exists

Embodied AI papers are growing too fast.

Important ideas are scattered across thousands of papers. Valuable research directions are often buried under sheer volume. It is hard to tell whether a topic has already become mainstream or is just beginning to explode if you are only tracking papers manually.

This project is built to compress that chaos into something actually useful: a field map, a trend detector, and a leaderboard that helps you surface the papers worth paying attention to.

## Homepage

Live site:

- https://dreamfallenflowers.github.io/Paper-Leaderboard-For-Robot-Manipulation/

## What This Repository Covers

This repository tracks arXiv papers related to **robot manipulation** since **2023-01-01**.

- Paper discovery source: **arXiv**
- Citation source: **Google Scholar**
- Keyword source: **automated extraction workflow**

## Three Ranking Modes

This leaderboard provides three views:

- **Overall**: total citation impact
- **Hot**: impact combined with recency
- **Newest**: sorted by publication date

In practice:

- **Overall** highlights papers that have already shaped the field
- **Hot** highlights papers that are rising quickly
- **Newest** helps you track the frontier directly

## Keyword Filtering

The current leaderboard contains **76 keywords** from automated extraction plus manual design. You can freely combine keywords in the search box.

Examples:

- `VLA + world model`
- `reinforcement learning + robotic manipulation - survey`
- `tactile + dexterous manipulation`

This makes it easy to drill down into the exact slice of the field you want to inspect.

## Notes on Keywords

The keyword extraction policy is intentionally conservative.

Keywords are meant to capture each paper's **core contribution**, not every technical ingredient that appears in the paper. A paper may use a benchmark, model component, training trick, or control element related to a tag, but if that element is not part of the paper's central contribution, the tag may not be extracted.

This is not a bug. It is a deliberate tradeoff: a cleaner and more useful tag system for real filtering and ranking, instead of a superficially broad but semantically noisy pile of labels.

## Score Formula

Leaderboard scores are determined by citation count and paper age.

Let:

- `cited_by_count`: cached Google Scholar citation count
- `age_days`: number of days since publication
- `lambda = 0.00075`

Then:

- `citation_factor = 1 + ln(1 + cited_by_count)`
- `freshness = exp(-lambda * age_days)`
- `Overall Score = citation_factor`
- `Hot Score = citation_factor * freshness`

Interpretation:

- **Overall Score**: logarithmically compressed citation impact
- **Hot Score**: citation impact discounted by age to surface papers that are rising quickly

## Data Files

This repository contains the final published outputs:

- `data/papers.min.json`: paper data used by the website
- `data/tags.json`: keyword statistics
- `data/aliases.json`: search alias mapping
- `data/stats.json`: site metadata
- `data/total_ranked.csv`: Overall ranking table
- `data/hot_ranked.csv`: Hot ranking table
- `data/ranked.csv`: full exported ranking table

## Update Plan

This leaderboard will be updated **once per month**.

At the same time, the full workflow will be open-sourced within **one week**, so anyone can directly reuse this pipeline to build a paper leaderboard for their own field. I sincerely hope this helps more people, and contributions are very welcome.
