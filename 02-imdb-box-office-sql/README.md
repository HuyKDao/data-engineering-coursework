# IMDb Box-Office Data Cleaning & Analysis in SQL

**Course:** Data 101, Data Engineering (UC Berkeley, Spring 2025), Project 1

**Question:** Using a real, messy IMDb database, which movies and actors drive the most box-office revenue?

## Data
A PostgreSQL `imdb` database with titles, ratings, cast and financial info stored as loosely structured key-value rows.

## What I did
- **Explored the schema:** used `information_schema` to understand the tables, then sampled rows randomly, both by percentage and by a fixed row count.
- **Cleaned data in SQL:** pulled MPAA ratings out of a generic `info_type` table, and parsed budget and gross earnings strings (currencies and formatting) into numeric columns.
- **Analyzed money:** computed earnings and profit per film, found the **top 10 most profitable films**, and joined cast tables to find the **highest-earning actors**.
- Ran the analyses on the cleaned views, comparing gross earnings across ratings and over time.

## Skills and tools
PostgreSQL, SQL data cleaning (string parsing, `CASE`, casting, regex), views, joins across normalized tables, sampling (`TABLESAMPLE`), pandas, Matplotlib, Seaborn.
