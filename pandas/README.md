# Pandas A to Z — The Complete Reference Notebook

A single, self-contained Jupyter notebook covering Pandas from first
principles to the techniques used in day-to-day AI/ML/DL data pipelines.

No external data files are required — every example builds its own sample
data inline, so you can clone this repo and run every cell immediately.

## Contents

1. Setup and Core Data Structures (`Series`, `DataFrame`)
2. Creating Series and DataFrames
3. Reading and Writing Data — CSV, Excel, JSON, Parquet, SQL pattern, chunked reads
4. Inspecting and Exploring Data
5. Selection and Indexing — `loc`, `iloc`, boolean masks, `query`
6. Editing Data — adding, dropping, renaming, dtype casting
7. Handling Missing Data — including a decision table for imputation strategy
8. Duplicates and Data Cleaning
9. Sorting and Ranking
10. Vectorized Operations, `map`, `apply` — with a performance-ordering explanation
11. GroupBy — split, apply, combine
12. Aggregation, Pivot Tables, and Cross-Tabulation
13. Merging, Joining, and Concatenating
14. Reshaping — `melt`, `pivot`, `stack`/`unstack`
15. MultiIndex (Hierarchical Indexing)
16. String Operations (`.str` accessor)
17. Date and Time Handling (`.dt` accessor, resampling, rolling windows)
18. Categorical Data
19. Window Functions — `rolling`, `expanding`, `ewm`
20. Combining and Updating DataFrames
21. Performance Optimization — with a benchmarked comparison table
22. Plotting with Pandas
23. Styling DataFrames
24. Options, Settings, and Display Configuration
25. Quick Reference Cheat-Sheet

## Running it

```bash
git clone <this-repo-url>
cd <this-repo-folder>
pip install pandas numpy matplotlib openpyxl pyarrow jupyter
jupyter notebook Pandas_A_to_Z.ipynb
```

## Why this notebook exists

Most Pandas tutorials cover isolated topics. This one is built as a single
linear reference: each section states *why* a technique matters, not just
its syntax, and includes a performance/decision-making note wherever the
"obvious" approach isn't actually the best one (e.g. imputation strategy,
`.apply()` vs vectorization, CSV vs Parquet).

## License

Feel free to use, fork, and adapt this for your own learning or teaching.
