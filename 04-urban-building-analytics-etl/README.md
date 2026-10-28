# Urban Building Analytics ETL

**Course:** Data 101, Data Engineering (UC Berkeley, Spring 2025), Project 3

**Question:** How do you turn raw, messy smart-building sensor data into analysis-ready tables?

## Data
A three-year dataset of building energy and occupancy sensors ([Luo et al., *Scientific Data*, 2022](https://doi.org/10.1038/s41597-022-01257-x)), loaded into PostgreSQL. Sensor metadata uses the **Brick** building ontology.

## What I did
An end-to-end ETL pipeline written in SQL:
1. **Unboxing:** explored and normalized nested sensor metadata into relational tables.
2. **Outliers:** flagged anomalous readings with **Hampel X84 intervals** (median ± k·MAD), then handled them with **winsorization**.
3. **Entity resolution:** standardized inconsistent location and sensor names with fuzzy matching.
4. **Missing data:** generated rows for missing timestamps and filled them with **linear interpolation**, built from forward and backward passes with window functions.
5. **Granularity transforms:** rolled readings up through the Brick ontology using a **recursive transitive `subClassOf` relation**.

## Skills and tools
PostgreSQL, SQL ETL, CTEs and recursive CTEs, window functions, outlier detection (Hampel/MAD), winsorization, entity resolution, time-series interpolation, ontologies, schema design.
