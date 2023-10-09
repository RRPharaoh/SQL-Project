What issues will you address by cleaning the data?

First issue I will address are the names and structures of the table. Ensuring consistency as well as correct formatting.
Followed by renaming and deleting unwanted/unneeded columns. Removing duplicate columns, and ensuring data completeness.
Altering names of rows,
changing types, changing formats, joining some tables.
Look for outliers.




Queries:
Below, provide the SQL queries you used to clean your data.

ALTER TABLE all_sessions
RENAME COLUMN V2ProductName TO v2_product_name;

ALTER TABLE all_sessions
ALTER COLUMN date TYPE DATE USING TO_DATE(CAST(date AS VARCHAR), 'YYYYMMDD');

UPDATE all_sessions
SET country = REPLACE(country, '(not set)', 'N/A')
WHERE country = '(not set)'

ALTER TABLE all_sessions
DROP COLUMN total_transaction_revenue, DROP COLUMN transactions, 
DROP COLUMN session_quality_dim, DROP COLUMN product_price, DROP COLUMN item_quantity,
DROP COLUMN item_revenue, DROP COLUMN transaction_revenue, DROP COLUMN transaction_id,
DROP COLUMN ecommerce_action_option;

alter table analytics
DROP COLUMN revenue

ALTER TABLE analytics
ALTER COLUMN date TYPE TEXT;

ALTER TABLE all_sessions
ALTER COLUMN date TYPE DATE USING TO_DATE(CAST(date AS VARCHAR), 'YYYYMMDD');

SELECT *
FROM all_sessions
WHERE currency_code IS NOT NULL AND currency_code <> 'USD'

UPDATE all_sessions
SET  currency_code = 'USD'
WHERE currency_code IS NULL;

Check for duplicate
Replacing values with N/A
UPDATE all_sessions
SET city = REPLACE(city, '(not set)', 'N/A')
WHERE city = '(not set)';
