# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
The primary goal of this project is to analyze and transform data from a PostgreSQL server, in order to find insight and draw conclusion about products being sold through ecommerce. 
my secondary goal is to continue to improve on my SQL proficiency as well as improve my familiarity with the Posgresql process.

## Process
Step 1
<em>clean the data, for consistency and uniformity.<em>
My initial process begins with normalizing the data and making readable,
I started by making adjustments to the columns. This included:
  - formatting columns for consistency:
  - deleting columns
  - renaming columns
  - Casting variable types, and even adjusting some columns mathematically.

Early on, I wasn't sure what data would be needed for analyzing and answering questions, a bit of cleanup was done after all the questions were answered.
After completing the questions portion, it became clear what information was absolutely not needed. 
Some columns were left untouched even after the fact, simply because I felt that the columns were relevant to the overall data. One such example was the 'Time_on_site' column in the ‘all_sessions’ table. I could not figure out how to adjust that column to make it easier to understand, as I did not understand the scale that was used to measure time, i.e. seconds, minutes, etc. 

Step 2
<em>Analyze the data, to find connection and draw some insight.<em>
I followed up by analyzing the data to gain some insight. 
I started by establishing a Primary keys and foreign keys between the tables. once I could confirm that these columns were complete and reliable, I then attempted to draw connections between the tables as many of the questions required data from multiple tables. I then established key information that the individual tables could provide, and what they couldn’t. 

## Results
The data included products with unique skus, as well as an array of customer information, some more informative, some not so much. It also included path tracing as well as impression data, which I thought was interesting as well. 
I relied on the questions provided to draw out more information than I could figure out at first glance. I also utilized the questions to draw some more conclusions from the data sets.
 
## Challenges 
One of my main challenges came with connecting the different tables to parse through the data and determine what was necessary from what wasn’t. The tables also had a lot of missing data, and that required me to decide where to fill in the blanks or to omit the columns in their entirety (particularly with the ‘all_sessions’ table). I tried to maintain as much consistency as possible.
Another issue I had was with some of the variables being off, or poorly formatted, which required me to do a bit of math or to CAST columns into different data types. I also attempted to answer some of the questions with missing data, specifically the questions that revolved around country and city of buyers. The missing data can definitely skew the results, which will definitely lead to some inconsistencies. But for the sake of the exercise, I answered as best I could.

## Future Goals
I would like to figure out how to accurately format the time columns, as I could not figure out how to calculate them. Also, I believe that the table can be organized to be more effective, and more consistent. 
One ting I did not take advantage of was creating my own tables. I only thought of it after the fact and realized that utilizing the joins function more often would create more ease of use. the ‘All_sessions’ table could be formatted to be more comprehensive and less chaotic. while, the ‘sales_by_sku’ table seems isolated and somewhat redundant. considering we have sales numbers on multiple tables. I think that the tables can definitely be reorganized, to find and calculate data much easier, while certain data columns can be excluded, even though they are complete. an example of this would be the ‘currency_code’ column; USD was the main currency utilized, and even for international orders. 


## Future Goals
I would like to figure out how to accurately format the time columns, as I could not figure out how to calculate them. Also, I believe that the table can be organized to be more effective, and more consistent. 
One ting I did not take advantage of was creating my own tables. I only thought of it after the fact and realized that utilizing the joins function more often would create more ease of use. the All_sessions table could be formatted to be more comprehensive and less chaotic. while, the 'sales_by_sku' table seems isolated and somewhat redundant. considering we have sales numbers on multiple tables. I think that the tables can definetly be reorganied, to find and calculate data much easier, while certain data columns can be excluded, even though they are complete. an example of this would be the currency_code column; USD was the main currency utilized, and even for international orders. 
