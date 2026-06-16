# Houston Rockets 2025-26 Season Review

A data-driven review of the Houston Rockets' 2025-26 NBA season. The report breaks down what worked, what didn't, and why — focusing on the structural roster issues that defined the year.

**[View the live report →](https://USERNAME.github.io/REPO-NAME/)**

(Replace `USERNAME` and `REPO-NAME` with your GitHub username and repo name once it's set up.)

## What's in the report

The report is a single tabbed HTML page covering:

- **Overview** — A numbered timeline of seven season-defining moments
- **Lineup Construction** — How VanVleet's preseason ACL tear forced a "fixed four + rotating fifth" starting lineup all year
- **Playstyle Identity** — Houston dominated the paint but their already-weak three-point shooting got worse
- **The Close-Out Problem** — Clutch performance regression year over year, four blown Q4 leads, and what happened when Durant sat
- **KD Reliance** — A 37-year-old Durant carrying a 31.9% share of Houston's scoring and ranking 1st in the NBA in gravity
- **Postseason & Beyond** — Game 3's final-minute collapse and the structural reasons it happened

The central argument: Houston's championship aspirations died at the trade deadline, when the front office didn't address the point guard hole VanVleet's injury opened up. The playoffs only confirmed what the regular season already showed.

## How it was built

Everything in the report comes from publicly available NBA data:

- **NBA Stats API** (via [`nba_api`](https://github.com/swar/nba_api)) — team and player game logs, advanced stats, clutch stats, shot charts, play-by-play
- **ESPN API** — play-by-play with quarter-break substitutions (used for 5-man lineup reconstruction)
- **NBA.com Inside the Game** — gravity tracking data (manually transcribed)

The full data pipeline + analysis lives in `notebook/rockets_season_review_25_26.ipynb`. Every API response is cached as a parquet file, so re-running is instant after the first pull.

## How to reproduce

```bash
pip install -r requirements.txt
jupyter notebook notebook/rockets_season_review_25_26.ipynb
```

Run cells top-to-bottom. The notebook is organized into clearly labeled sections matching the report's structure.

## Repo structure

```
.
├── index.html                                  # the standalone report (this is what GitHub Pages serves)
├── notebook/
│   └── rockets_season_review_25_26.ipynb       # full data pipeline + analysis
├── requirements.txt
└── README.md
```

## Notes on methodology

- "Clutch" follows the NBA's official definition: last 5 minutes with the score within 5 points
- "Stretch" in the KD-off analysis means one continuous on-off period within a game
- "Fixed four" refers to the starting four players who never changed: Amen Thompson, Alperen Sengun, Jabari Smith Jr., Kevin Durant
- "Gravity" is a tracking metric from NBA.com that measures defensive attention drawn above what floor spacing predicts
- Seasons cover 2024-25 and 2025-26 regular season + playoffs

## License

This is a personal portfolio project. Code is free to read and learn from; the analysis and report content are the author's own work.
