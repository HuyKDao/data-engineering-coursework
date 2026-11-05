# Yelp Insight Engine with MongoDB

**Course:** Data 101, Data Engineering (UC Berkeley, Spring 2025), Project 4

**Question:** How do you query and model semi-structured JSON data, and when should it live in MongoDB, PostgreSQL or pandas?

## Data
The [Yelp Academic Dataset](https://www.yelp.com/dataset): businesses, users and reviews as JSON.

## What I did
- **MongoDB queries (MQL):** filters, projections, updates and multi-stage **aggregation pipelines**. For example, computing average ratings and ranking top-rated cities per state.
- **Text search:** built a text index to find **728 reviews** with negative keywords and labeled them.
- **JSON vs. relational:** loaded **7,500 reviews** into PostgreSQL and compared JSON querying in SQL with MongoDB.
- **pandas:** flattened nested documents into DataFrames for analysis.
- **Messy JSON:** cleaned inconsistent nested fields and missing keys.

## Skills and tools
MongoDB, PyMongo, aggregation pipelines, text indexes, PostgreSQL JSON functions, pandas (`json_normalize`), semi-structured data modeling.
