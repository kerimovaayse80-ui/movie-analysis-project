#  Movie Analysis Project

An end-to-end data analytics pipeline built for the CodeAlpha Data Analytics
internship, covering 3 tasks: Web Scraping, Exploratory Data Analysis, and
Data Visualization — all built on one dataset: Academy Award-winning films
(1934-2025).

## Project Overview

This project scrapes Academy Award-winning film data from Wikipedia, cleans
and explores it, and visualizes key trends across decades — analyzing the
relationship between nominations, wins, and time.

## Pipeline

1. **Web Scraping** (`scraping/SCRAPING.ipynb`) — Scraped the list of Academy
   Award-winning films from Wikipedia (1,336 films). → `data/movies_raw.csv`
2. **EDA** (`eda/EDA.ipynb`) — Cleaned and explored the data: fixed data
   types, checked for missing values/duplicates, analyzed trends across
   decades. → `data/movies_clean.csv`
3. **Data Visualization** (`visuals/visualization.ipynb`) — 5 charts
   visualizing decade trends, award distribution, nominations vs. awards,
   and the most-awarded films of all time.

## Setup

```bash
pip install requests beautifulsoup4 pandas lxml matplotlib jupyterlab
jupyter lab
```

## Folder Structure

```
CodeAlpha_MovieAnalytics/
├── scraping/
│   └── SCRAPING.ipynb
├── eda/
│   └── EDA.ipynb
├── visuals/
│   ├── visualization.ipynb
│   ├── movies_per_decade.png
│   ├── awards_distribution.png
│   ├── nominations_vs_awards.png
│   ├── trend_by_decade.png
│   └── top10_films.png
├── data/
│   ├── movies_raw.csv
│   └── movies_clean.csv
├── .gitignore
└── README.md
```

## Key Findings

- Analyzed 1,279 Academy Award-winning films (1934-2025) after cleaning
- Award-winning films peaked in the 1940s (166 films); the 1930s and 2020s
  show fewer films (2020s data is still incomplete since the decade isn't over)
- Average win rate (awards won ÷ nominations received) is 64%, with a median of 50%
- Nominations have risen steadily over time (3.44 avg in the 1930s → 4.41 avg
  in the 2020s), while awards per film stayed relatively flat (~1.6-1.7) —
  likely reflecting the Academy expanding award categories over the decades
- Nominations and Awards show a moderate positive correlation (r = 0.69)
- Most-awarded films: *Ben-Hur*, *Titanic*, and *The Lord of the Rings: The
  Return of the King* (11 awards each)

## Tools Used

- **Web Scraping:** `requests`, `BeautifulSoup4`
- **Data Analysis:** `pandas`
- **Visualization:** `matplotlib`

## Author

Ayshe — CodeAlpha Data Analytics Internship
