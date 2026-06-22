# NHL Player Value Dashboard

Analysis of NHL player performance relative to salary (AAV) for the 2024–25 season, broken down by position group.

## Metrics

| Position | Metric |
|----------|--------|
| Forwards | Points per $1M AAV |
| Defensemen | Shots Blocked per $1M AAV |
| Goalies | Goals Saved per $1M AAV |

## Data Sources

- **skaters.csv / goalies.csv** — Per-player stats from [Natural Stat Trick](https://www.naturalstattrick.com/), `situation = all` (full season, all situations)
- **salaries.csv** — Current contract AAV from public salary data

## Setup

```bash
pip install pandas matplotlib
jupyter notebook analysis.ipynb
```

## Outputs

Running the notebook generates:

- `forwards_value.png` — Scatter plot of forward salary vs. points per $1M
- `defense_value.png` — Scatter plot of defenseman salary vs. shots blocked per $1M
- `goalies_value.png` — Scatter plot of goalie salary vs. goals saved per $1M
- `nhl_value_dashboard.png` — Combined three-panel dashboard

## Notes

- Only players with matching salary records are included (players on entry-level or expiring contracts without data in salaries.csv are excluded).
- Goals saved = shots on goal faced − goals allowed.
- All stats filtered to `situation = "all"` to avoid double-counting special teams rows.
