# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
The goal of this project is to analyze and transform data from a PostgreSQL server, in order to find insight and draw conclusion about products being sold through ecommerce.

## Process
Step 1
clean the data, for consistency and uniformity.

Step 2
Analyze the data, to find connection and draw some insight. 

## Results
The data included products with unique skus, as well as an array of customer information, some more informative, some not so much. It also included path tracing as well as impression data, which I thought was interesting as well. 

## Challenges 
One of my main challenges came with connecting the different tables in order to parse through the data and determine what was necessary from what wasn’t. The tables also had a lot of missing data, and that required me to decide where to fill in the blanks or to omit the columns in their entirety (particularly with the all_sessions table). I tried to maintain as much consistency as possible.
Another issue I had was with some of the variables being off, or poorly formatted, which required me to do a bit of math or to CAST columns into different data types. I also attempted to answer some of the questions with missing data, specifically the questions that revolved around country and city of buyers. The missing data can definitely sk.ew the results, which will definitely lead to some inconsistencies. But for the sake of the exercise, I answered as best I could.

## Future Goals
I would like to figure out how to accurately format the time columns, as I could not figure out how to calculate them. Also, I believe that the table can be organized to be more effective, and more consistent. 

