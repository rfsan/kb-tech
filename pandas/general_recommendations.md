# Pandas - General Recommendations

- Use groupby

  - `aggregate` (alias `agg`) to reduce a group to one result (e.g. mean)
    
    My favorite syntax is [named aggregation](https://pandas.pydata.org/docs/user_guide/groupby.html#named-aggregation)
    
    ```python
    animals.groupby('kind').agg(
        # result_column_name = ( animals_column, agg_func or lambda)
        min_height=("height", "min"),
        max_height=("height", "max"),
        average_weight=("weight", "mean"),
    )
    ```
    
  - `transform` to compute an operation that returns the same number of rows (e.g. cumsum, fillna)
  
- Use crosstab (can do the same as pivot and more)
- Use pyarrow
- Use merge

## Configurations I like

```python
pd.set_option("display.max_columns", None)
pd.set_option("plotting.backend", "plotly")
```