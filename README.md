# Robot Manipulation Knowledge Base

[中文说明 / Chinese Version](./README.zh-CN.md)

This project is a living leaderboard for robot manipulation papers. It is built to answer a simple but annoyingly hard question: **what are the most important, most influential, and most worth-tracking papers in robot manipulation right now?**

## Homepage

- GitHub Pages: https://dreamfallenflowers.github.io/Paper-Leaderboard-For-Robot-Manipulation/

## What This Repository Covers

This repository tracks arXiv papers related to **robot manipulation** from **2023-01-01** to the latest update time of this project.

- Paper discovery comes from arXiv
- Citation counts come from Google Scholar via cached lookup
- Keywords are produced by an automated extraction workflow

The result is not just a static list. It is a searchable, combinable, updateable map of the field.

## Three Ranking Modes

This leaderboard supports three different ranking views:

- **Overall**: total citation impact
- **Hot**: combined impact and recency
- **Newest**: ranking by publication date

The scoring formulas are:

- `citation_factor = 1 + ln(1 + cited_by_count)`
- `freshness = exp(-0.00075 * age_days)`
- `Overall Score = citation_factor`
- `Hot Score = citation_factor * freshness`

In practice:

- **Overall** highlights the papers that have already shaped the field
- **Hot** surfaces the papers that are rising fast right now
- **Newest** lets you watch the frontier as it moves

## Keyword Filtering

This leaderboard currently contains **76 keywords**.

You can freely combine them in the search box to build your own slice of the field:

- `a + b`
- `a + b - c`

That means you can instantly drill down into specific directions, such as methods, control families, datasets, world models, VLA work, tactile work, sim-to-real, and many more.

## Important Note on Keywords

Keywords in this project are intentionally **conservative**.

They are designed to capture the **core contribution** of each paper, not every ingredient mentioned in the paper. So a paper may use a technique, benchmark, or modeling element related to a given tag, but if that element is not one of the paper's central contributions, that tag may not be extracted.

This tradeoff is deliberate: the goal is cleaner retrieval and more meaningful subfield ranking, not maximal tag coverage at any cost.

## Update Plan

This leaderboard is updated **once per month**.

The full workflow used to build it will be open-sourced within **one week**, so you can adapt the same pipeline to create a paper leaderboard for your own field.

## Data Files

This repository includes the final published outputs:

- `data/papers.min.json`: compact paper records used by the web UI
- `data/tags.json`: canonical keyword counts
- `data/aliases.json`: keyword alias map for search suggestions
- `data/stats.json`: site metadata
- `data/total_ranked.csv`: ranking by Overall Score
- `data/hot_ranked.csv`: ranking by Hot Score
- `data/ranked.csv`: full exported ranking table

## Why This Exists

The robot manipulation literature is exploding. Important ideas are scattered across thousands of papers, and the signal is buried under volume.

This project is meant to be a sharper tool: a field map, a trend detector, and a fast filter for researchers who want to know not just **what exists**, but **what matters**.
