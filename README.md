# Robot Manipulation Knowledge Base

This repository publishes the final static website and ranking tables for the Robot Manipulation Knowledge Base.

## Website

The GitHub Pages site is served directly from the repository root.

## Data Files

The repository includes final ranking outputs:

- `data/papers.min.json`: compact paper records used by the web UI
- `data/tags.json`: canonical keyword counts
- `data/aliases.json`: keyword alias map for search suggestions
- `data/stats.json`: site metadata
- `data/total_ranked.csv`: ranking by Overall Score
- `data/hot_ranked.csv`: ranking by Hot Score
- `data/ranked.csv`: full exported ranking table

## Score Formula

The ranking scores are computed from citation count and paper age.

Let:

- `cited_by_count` be the cached Google Scholar / Serper citation count
- `age_days` be the number of days since publication
- `lambda = 0.00075`

Then:

- `citation_factor = 1 + ln(1 + cited_by_count)`
- `freshness = exp(-lambda * age_days)`
- `Overall Score = citation_factor`
- `Hot Score = citation_factor * freshness`

Interpretation:

- **Overall Score** measures total citation impact with logarithmic compression.
- **Hot Score** measures citation impact discounted by age, so newer fast-rising papers can surface.

## Current Snapshot

- Indexed papers: 11038
- Citation-enriched papers: 1701
- Citation refresh finished at: 2026-06-24 15:42 UTC

## Scope

This publish-only repository contains final web assets and ranking outputs. It does not include the local crawling, filtering, or pipeline code used to generate them.
