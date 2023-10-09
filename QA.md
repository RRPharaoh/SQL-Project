What are your risk areas? Identify and describe them.
Missing variables within the all_sesions table. While there are numerous missing values, there are columns are too important to outright omit while others can be dropped. My solution will be the plug in the variables where I can, and fill rows with missing variables and if necessary, delete rows/columns. also, many of the column are incorrectly formatted, I will need to address them by correctly formatting. Repeat variables within the id column are also risk factors that can skew data.


QA Process:
Describe your QA process and include the SQL queries used to execute it.


 Checking for duplicates within the products table 
 example
 SELECT sku, COUNT(*) AS count
FROM products
GROUP BY sku
HAVING COUNT(*) > 1;

cheking for Null/missing values within tables values 
SELECT *
FROM all_sessions
WHERE visit_id IS NULL;

SELECT *
FROM all_sessions
WHERE country = '(not set)'
