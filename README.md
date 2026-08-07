\# CodeAlpha Movie Analytics



An end-to-end data analytics pipeline built for the CodeAlpha Data Analytics

internship, covering all 4 tasks: Web Scraping, Exploratory Data Analysis,

Sentiment Analysis, and Data Visualization — all connected through one

dataset: Academy Award-winning films (1934-2025).



\## Project Overview



This project scrapes Academy Award-winning film data from Wikipedia, cleans

and explores it, visualizes key trends, and analyzes the sentiment of critical

reception text for the most-awarded films — testing whether positive reviews

actually correlate with award success.



\## Pipeline



1\. \*\*Web Scraping\*\* (`scraping/SCRAPING.ipynb`) — Scraped the list of Academy

&#x20;  Award-winning films from Wikipedia (1,336 films), plus critical reception

&#x20;  text for the top 30 most-awarded films from their individual Wikipedia

&#x20;  pages. → `data/movies\_raw.csv`

2\. \*\*EDA\*\* (`eda/EDA.ipynb`) — Cleaned and explored the data: fixed data

&#x20;  types, checked for missing values/duplicates, analyzed trends across

&#x20;  decades. → `data/movies\_clean.csv`

3\. \*\*Sentiment Analysis\*\* (`sentiment/sentiment.ipynb`) — Used VADER to score

&#x20;  critical reception text for the top 30 most-awarded films, classified

&#x20;  sentiment, and tested correlation with Awards won. → `data/reviews\_with\_sentiment.csv`

4\. \*\*Data Visualization\*\* (`visuals/visualization.ipynb`) — 5 charts

&#x20;  visualizing decade trends, award distribution, nominations vs. awards,

&#x20;  and the most-awarded films of all time.



\## Setup



```bash

pip install requests beautifulsoup4 pandas lxml nltk matplotlib jupyterlab

jupyter lab

```



\## Folder Structure



```

CodeAlpha\_MovieAnalytics/

├── scraping/

│   └── SCRAPING.ipynb

├── eda/

│   └── EDA.ipynb

├── sentiment/

│   └── sentiment.ipynb

├── visuals/

│   ├── visualization.ipynb

│   ├── movies\_per\_decade.png

│   ├── awards\_distribution.png

│   ├── nominations\_vs\_awards.png

│   ├── trend\_by\_decade.png

│   └── top10\_films.png

├── data/

│   ├── movies\_raw.csv

│   ├── movies\_clean.csv

│   └── reviews\_with\_sentiment.csv

├── .gitignore

└── README.md

```



\## Key Findings



\*\*EDA:\*\*

\- Analyzed 1,279 Academy Award-winning films (1934-2025) after cleaning

\- Award-winning films peaked in the 1940s (166 films); the 1930s and 2020s

&#x20; show fewer films (2020s data is still incomplete since the decade isn't over)

\- Average win rate (awards won ÷ nominations received) is 64%, with a median of 50%

\- Nominations have risen steadily over time (3.44 avg in the 1930s → 4.41 avg

&#x20; in the 2020s), while awards per film stayed relatively flat (\~1.6-1.7) —

&#x20; likely reflecting the Academy expanding award categories over the decades

\- Nominations and Awards show a moderate positive correlation (r = 0.69)

\- Most-awarded films: \*Ben-Hur\*, \*Titanic\*, and \*The Lord of the Rings: The

&#x20; Return of the King\* (11 awards each)



\*\*Sentiment Analysis:\*\*

\- Scraped critical reception text for the top 30 most-awarded films (27/30

&#x20; successfully retrieved from Wikipedia)

\- Used VADER (lexicon-based sentiment analysis) to score each film's

&#x20; reception text, then classified it as positive/negative/neutral

\- 26 of 27 films scored as positive, which makes sense given these are all

&#x20; critically significant, award-winning films

\- \*\*Notable exception:\*\* \*Cabaret\* (1972) scored strongly negative (-0.91)

&#x20; despite genuinely positive reviews. This happens because VADER analyzes

&#x20; text word-by-word — critics used words like "bleak," "despair," and

&#x20; "cynical" to praise how well the film captured its dark subject matter

&#x20; (Nazi-era Germany), but VADER can't distinguish between negative words

&#x20; \*describing content\* and negative words \*expressing opinion\*. This

&#x20; reveals a genuine, well-documented limitation of lexicon-based sentiment

&#x20; tools on long, thematically complex text.

\- Correlation between sentiment score and Awards won: essentially zero

&#x20; (r = -0.002; r = 0.115 excluding the Cabaret outlier) — suggesting that

&#x20; how positively critics write about a film has little relationship with how

&#x20; many Oscars it wins. Award success likely depends more on factors like

&#x20; campaign strategy, timing, and industry/branch voting patterns than on

&#x20; critical sentiment alone.



\## Tools Used



\- \*\*Web Scraping:\*\* `requests`, `BeautifulSoup4`

\- \*\*Data Analysis:\*\* `pandas`

\- \*\*Visualization:\*\* `matplotlib`

\- \*\*Sentiment Analysis:\*\* `nltk` (VADER)



\## Author



Ayshe — CodeAlpha Data Analytics Internship

