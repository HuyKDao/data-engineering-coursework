# PostgreSQL Query Performance Tuning

**Course:** Data 101, Data Engineering (UC Berkeley, Spring 2025), Project 2

**Question:** Why are some SQL queries slow, and how do views, join strategies and indexes change their cost?

## Data
[Lahman's Baseball Database](http://seanlahman.com/): batting, pitching, teams and Hall of Fame data from 1871 to 2020, loaded into PostgreSQL.

## What I did
- Read **`EXPLAIN ANALYZE`** query plans to find where time is spent.
- Compared **views and materialized views**, and checked **predicate pushdown** to see when filters run early.
- Compared **join algorithms** (nested loop, hash, merge) and when the planner picks each one.
- **Indexing experiments:**
  - Single-column and **multi-column indexes**.
  - Indexes that speed up **aggregations**.
  - **Clustered indexes**.
  - The **cost of maintaining indexes** on inserts and updates.
- Explained each design choice in writing.

## Results
Times are from one `EXPLAIN ANALYZE` run each, in milliseconds.

| Change | Before (ms) | After (ms) |
|---|---|---|
| Materialized view instead of a regular view | 4.87 | 0.173 |
| Index on the filter column of a salary join | 16.0 | 8.0 |
| Indexes for a join with an AND filter | 13.5 | 4.9 |
| Multi-column index for a join with an OR filter | 17.4 | 8.0 |
| Index for a `MIN` aggregation | 3.9 | 0.1 |
| Index on the filter column, then clustering the table on it | 11.6 | 2.1 |

Clustering the table on its primary key didn't help (11.6 → 12.3 ms), because the query filters on a different column.

## Skills and tools
PostgreSQL, query plans (`EXPLAIN ANALYZE`), indexing (B-tree, multi-attribute, clustered), views and materialized views, join algorithms, performance tuning, JupySQL.
