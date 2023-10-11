### What are your risk areas? Identify and describe them.

- Missing Data in key areas of the tables. 
  While there are numerous missing values, there are columns are too important to outright omit while others can be dropped. My solution will be the plug in the variables where I can, and fill rows with missing variables and if necessary, delete rows/columns. 

- Incorectly formatted columns.
  many of the column are incorrectly formatted, which can skew data, and provide inconsistent analysis.
  
- Repeat variables
  There are repeat variables throughout the tables, that can skew data.


### QA Process:
<em>Describe your QA process and include the SQL queries used to execute it.<em>

- I started by ensuring that every product had a unique sku that only appeared once. This was done with the following query.
- This was followed by checking for Null/missing values within tables values that may not have been accounted for. 
- I also made some adjustments in response to feedback I received, to ensure that some values N/A wasn't accounted for as a value.
- My last step was to manually spot check certain tables for completeness, and proper formatting.

```
  SELECT sku, COUNT(*) AS count
  FROM products
  GROUP BY sku
  HAVING COUNT(*) > 1;
```


```
  SELECT *
  FROM all_sessions
  WHERE visit_id IS NULL;
```

```
  SELECT *
  FROM all_sessions
  WHERE country = '(not set)'
```
```
  update all_sessions
  set country = NULL
  WHERE country = 'N/A'
```