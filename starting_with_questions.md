Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


### SQL Queries: 

  SELECT *
  FROM all_sessions
  INNER JOIN sales_report ON all_sessions.product_sku = sales_report.product_sku;

  SELECT country, COUNT(DISTINCT full_visitor_id) as transactions
  FROM all_sessions
  GROUP BY country
  ORDER BY transactions DESC
  LIMIT 10;

  SELECT *
  FROM all_sessions
  INNER JOIN sales_report ON all_sessions.product_sku = sales_report.product_sku;

  SELECT city, COUNT(DISTINCT full_visitor_id) as transactions
  FROM all_sessions
  GROUP BY city
  ORDER BY transactions DESC
  LIMIT 10;

Answer:
| "Country"        | Highest Level of Transaction |
|------------------|------------------------------|
| "United States"  | 8118                         |
| "India"          | 693                          |
| "United Kingdom" | 641                          |
| "Canada"         | 607                          |
| "Germany"        | 321                          |
| "Japan"          | 233                          |
| "Australia"      | 219                          |
| "France"         | 205                          |
| "Taiwan"         | 160                          |
| "Netherlands"    | 154                          |



| "City"          | Highest Level of Transaction |
|-----------------|------------------------------|
| "Mountain View" | 1085                         |
| "New York"      | 603                          |
| "San Francisco" | 432                          |
| "Sunnyvale"     | 343                          |
| "San Jose"      | 228                          |
| "Los Angeles"   | 206                          |
| "London"        | 190                          |
| "Chicago"       | 178                          |
| "Toronto"       | 123                          |
| "Netherlands"   | 154                          |







**Question 2: What is the average number of products ordered from visitors in each city and country?**


### SQL Queries:
 
  SELECT all_sessions.country, ROUND(AVG(sales_by_sku.total_ordered),2)
  AS average_units_ordered
  FROM sales_by_sku
  INNER JOIN all_sessions ON sales_by_sku.product_sku = all_sessions.product_sku
  GROUP BY all_sessions.country 
  ORDER BY average_units_ordered DESC;





Answer:
| Country                | Average # of visitors|
|------------------------|--------------------|
| "Saudi Arabia"         | 96.29  |   |   |   |
| "Kuwait"               | 85.75  |   |   |   |
| "Ethiopia"             | 85.00  |   |   |   |
| "Oman"                 | 85.00  |   |   |   |
| "Laos"                 | 85.00  |   |   |   |
| "Papua New Guinea"     | 57.50  |   |   |   |
| "Honduras"             | 56.00  |   |   |   |
| "Croatia"              | 51.70  |   |   |   |
| "United Arab Emirates" | 47.36  |   |   |   |
| "Trinidad & Tobago"    | 47.00  |   |   |   |
| "Kazakhstan"           | 43.00  |   |   |   |
| "Greece"               | 36.58  |   |   |   |
| "South Korea"          | 36.38  |   |   |   |
| "Hong Kong"            | 35.90  |   |   |   |
| "Guatemala"            | 33.13  |   |   |   |
| "Czechia"              | 32.17  |   |   |   |
| "Réunion"              | 32.00  |   |   |   |
| "Mauritius"            | 31.00  |   |   |   |
| "Nepal"                | 30.50  |   |   |   |
| "Morocco"              | 30.33  |   |   |   |
| "Moldova"              | 30.00  |   |   |   |
| "Montenegro"           | 30.00  |   |   |   |
| "Mali"                 | 30.00  |   |   |   |
| "Italy"                | 30.00  |   |   |   |
| "Spain"                | 28.84  |   |   |   |
| "Denmark"              | 28.38  |   |   |   |
| "Germany"              | 27.56  |   |   |   |
| "Taiwan"               | 27.51  |   |   |   |
| "Japan"                | 27.28  |   |   |   |
| "Romania"              | 26.88  |   |   |   |
| "Ukraine"              | 26.85  |   |   |   |
| "Brazil"               | 26.07  |   |   |   |
| "Mexico"               | 25.94  |   |   |   |
| "Thailand"             | 25.46  |   |   |   |
| "San Marino"           | 25.00  |   |   |   |
| "Ireland"              | 24.20  |   |   |   |
| "Bulgaria"             | 24.11  |   |   |   |
| "Malaysia"             | 24.00  |   |   |   |
| "Israel"               | 23.92  |   |   |   |
| "Myanmar (Burma)"      | 23.67  |   |   |   |
| "Pakistan"             | 23.07  |   |   |   |
| "Portugal"             | 23.00  |   |   |   |
| "Slovenia"             | 23.00  |   |   |   |
| "Russia"               | 22.88  |   |   |   |
| "Georgia"              | 22.75  |   |   |   |
| "Singapore"            | 21.95  |   |   |   |
| "United States"        | 20.79  |   |   |   |
| "Argentina"            | 20.71  |   |   |   |
| "United Kingdom"       | 20.71  |   |   |   |
| "Colombia"             | 20.69  |   |   |   |
| "Venezuela"            | 20.06  |   |   |   |
| "Canada"               | 19.85  |   |   |   |
| "Netherlands"          | 19.14  |   |   |   |
| "Australia"            | 18.67  |   |   |   |
| "N/A"                  | 18.15  |   |   |   |
| "Vietnam"              | 18.14  |   |   |   |
| "Macedonia (FYROM)"    | 17.67  |   |   |   |
| "India"                | 17.38  |   |   |   |
| "Albania"              | 16.67  |   |   |   |
| "Belgium"              | 16.16  |   |   |   |
| "Armenia"              | 16.00  |   |   |   |
| "Kyrgyzstan"           | 16.00  |   |   |   |
| "Costa Rica"           | 15.80  |   |   |   |
| "Côte d’Ivoire"        | 15.50  |   |   |   |
| "Indonesia"            | 15.50  |   |   |   |
| "Slovakia"             | 15.50  |   |   |   |
| "Switzerland"          | 15.46  |   |   |   |
| "Panama"               | 15.00  |   |   |   |
| "Peru"                 | 14.85  |   |   |   |
| "Tunisia"              | 14.75  |   |   |   |
| "Philippines"          | 14.70  |   |   |   |
| "France"               | 14.55  |   |   |   |
| "Turkey"               | 13.67  |   |   |   |
| "Sweden"               | 13.39  |   |   |   |
| "Uganda"               | 13.00  |   |   |   |
| "Paraguay"             | 13.00  |   |   |   |
| "Poland"               | 12.81  |   |   |   |
| "Puerto Rico"          | 12.33  |   |   |   |
| "Finland"              | 12.27  |   |   |   |
| "Dominican Republic"   | 12.11  |   |   |   |
| "Zimbabwe"             | 12.00  |   |   |   |
| "New Zealand"          | 11.84  |   |   |   |
| "Hungary"              | 11.67  |   |   |   |
| "Bahrain"              | 11.50  |   |   |   |
| "Lithuania"            | 11.22  |   |   |   |
| "Nigeria"              | 11.17  |   |   |   |
| "Jersey"               | 11.00  |   |   |   |
| "Chile"                | 10.25  |   |   |   |
| "Serbia"               | 9.71   |   |   |   |
| "South Africa"         | 9.67   |   |   |   |
| "Egypt"                | 9.10   |   |   |   |
| "Tanzania"             | 9.00   |   |   |   |
| "Algeria"              | 9.00   |   |   |   |
| "Uruguay"              | 8.67   |   |   |   |
| "Ghana"                | 7.50   |   |   |   |
| "Norway"               | 7.30   |   |   |   |
| "El Salvador"          | 6.50   |   |   |   |
| "Bangladesh"           | 6.36   |   |   |   |
| "Austria"              | 5.53   |   |   |   |
| "Botswana"             | 5.00   |   |   |   |
| "Sri Lanka"            | 5.00   |   |   |   |
| "Nicaragua"            | 5.00   |   |   |   |
| "Jordan"               | 5.00   |   |   |   |
| "China"                | 4.39   |   |   |   |
| "Bolivia"              | 4.00   |   |   |   |
| "Cambodia"             | 3.25   |   |   |   |
| "Latvia"               | 3.17   |   |   |   |
| "Jamaica"              | 3.00   |   |   |   |
| "Palestine"            | 3.00   |   |   |   |
| "Bahamas"              | 2.50   |   |   |   |
| "Cyprus"               | 2.50   |   |   |   |
| "Estonia"              | 2.25   |   |   |   |
| "Brunei"               | 2.00   |   |   |   |
| "Sint Maarten"         | 2.00   |   |   |   |
| "Bosnia & Herzegovina" | 2.00   |   |   |   |
| "Martinique"           | 2.00   |   |   |   |
| "Belarus"              | 2.00   |   |   |   |
| "Macau"                | 2.00   |   |   |   |
| "Gibraltar"            | 2.00   |   |   |   |
| "Ecuador"              | 1.67   |   |   |   |
| "Qatar"                | 1.33   |   |   |   |
| "Kosovo"               | 1.00   |   |   |   |
| "Maldives"             | 1.00   |   |   |   |
| "Kenya"                | 0.67   |   |   |   |
| "Iraq"                 | 0.50   |   |   |   |
| "Malta"                | 0.00   |   |   |   |
| "Iceland"              | 0.00   |   |   |   |


| Cities                 |Average |
|------------------------|--------|
| "Brno"                 | 319.00 |   |   |   |
| "Riyadh"               | 319.00 |   |   |   |
| "Rexburg"              | 250.50 |   |   |   |
| "Lisbon"               | 189.00 |   |   |   |
| "Sacramento"           | 189.00 |   |   |   |
| "Kalamazoo"            | 105.00 |   |   |   |
| "Saint Petersburg"     | 101.25 |   |   |   |
| "Avon"                 | 100.00 |   |   |   |
| "Rome"                 | 97.75  |   |   |   |
| "Longtan District"     | 97.00  |   |   |   |
| "Sherbrooke"           | 97.00  |   |   |   |
| "Nashville"            | 94.00  |   |   |   |
| "Dubai"                | 89.20  |   |   |   |
| "Shinjuku"             | 73.00  |   |   |   |
| "Pune"                 | 71.08  |   |   |   |
| "Westville"            | 70.00  |   |   |   |
| "Rio de Janeiro"       | 65.33  |   |   |   |
| "Bellingham"           | 62.00  |   |   |   |
| "Vladivostok"          | 62.00  |   |   |   |
| "Santa Fe"             | 60.00  |   |   |   |
| "San Antonio"          | 58.17  |   |   |   |
| "Seoul"                | 57.65  |   |   |   |
| "Menlo Park"           | 51.50  |   |   |   |
| "Athens"               | 51.25  |   |   |   |
| "Palo Alto"            | 48.19  |   |   |   |
| "Salem"                | 46.19  |   |   |   |
| "Zhongli District"     | 46.00  |   |   |   |
| "Indore"               | 44.00  |   |   |   |
| "Belo Horizonte"       | 43.00  |   |   |   |
| "Boston"               | 40.47  |   |   |   |
| "Bangkok"              | 38.37  |   |   |   |
| "Hanoi"                | 37.67  |   |   |   |
| "Hong Kong"            | 36.49  |   |   |   |
| "Santa Clara"          | 36.00  |   |   |   |
| "Pozuelo de Alarcon"   | 34.33  |   |   |   |
| "Hamburg"              | 34.25  |   |   |   |
| "Munich"               | 33.25  |   |   |   |
| "Phoenix"              | 32.20  |   |   |   |
| "San Bruno"            | 31.75  |   |   |   |
| "Dublin"               | 31.33  |   |   |   |
| "Bellflower"           | 30.00  |   |   |   |
| "Cork"                 | 30.00  |   |   |   |
| "Milan"                | 26.40  |   |   |   |
| "Mumbai"               | 26.38  |   |   |   |
| "Tel Aviv-Yafo"        | 26.21  |   |   |   |
| "Toronto"              | 25.62  |   |   |   |
| "Seattle"              | 25.60  |   |   |   |
| "Mississauga"          | 24.67  |   |   |   |
| "Madrid"               | 24.58  |   |   |   |
| "Los Angeles"          | 24.52  |   |   |   |
| "Charlotte"            | 24.18  |   |   |   |
| "Irvine"               | 23.63  |   |   |   |
| "Montreuil"            | 23.00  |   |   |   |
| "Mountain View"        | 22.89  |   |   |   |
| "Buenos Aires"         | 22.25  |   |   |   |
| "Pittsburgh"           | 22.22  |   |   |   |
| "Amsterdam"            | 22.11  |   |   |   |
| "Ann Arbor"            | 22.00  |   |   |   |
| "Melbourne"            | 21.97  |   |   |   |
| "Chicago"              | 21.94  |   |   |   |
| "Austin"               | 21.74  |   |   |   |
| "San Francisco"        | 21.65  |   |   |   |
| "Vancouver"            | 21.00  |   |   |   |
| "Santiago"             | 20.75  |   |   |   |
| "Bogota"               | 20.40  |   |   |   |
| "N/A"                  | 20.40  |   |   |   |
| "Philadelphia"         | 19.94  |   |   |   |
| "Sydney"               | 19.93  |   |   |   |
| "Redmond"              | 19.67  |   |   |   |
| "Calgary"              | 19.50  |   |   |   |
| "San Jose"             | 19.04  |   |   |   |
| "Sao Paulo"            | 18.88  |   |   |   |
| "Kitchener"            | 18.80  |   |   |   |
| "Kolkata"              | 18.60  |   |   |   |
| "Oakland"              | 18.50  |   |   |   |
| "Berlin"               | 18.43  |   |   |   |
| "New York"             | 18.39  |   |   |   |
| "Sunnyvale"            | 18.09  |   |   |   |
| "Cupertino"            | 18.00  |   |   |   |
| "Ahmedabad"            | 18.00  |   |   |   |
| "London"               | 17.97  |   |   |   |
| "Ho Chi Minh City"     | 17.89  |   |   |   |
| "Redwood City"         | 17.83  |   |   |   |
| "Chennai"              | 17.54  |   |   |   |
| "Hyderabad"            | 17.44  |   |   |   |
| "Barcelona"            | 17.15  |   |   |   |
| "Houston"              | 16.66  |   |   |   |
| "Copenhagen"           | 16.00  |   |   |   |
| "Warsaw"               | 16.00  |   |   |   |
| "Ghent"                | 16.00  |   |   |   |
| "Kuala Lumpur"         | 15.90  |   |   |   |
| "Bucharest"            | 15.29  |   |   |   |
| "Prague"               | 15.00  |   |   |   |
| "Singapore"            | 14.30  |   |   |   |
| "Quebec City"          | 14.00  |   |   |   |
| "Perth"                | 14.00  |   |   |   |
| "Budapest"             | 14.00  |   |   |   |
| "Paris"                | 13.44  |   |   |   |
| "Lake Oswego"          | 13.33  |   |   |   |
| "La Victoria"          | 13.33  |   |   |   |
| "Montreal"             | 13.31  |   |   |   |
| "Dallas"               | 13.09  |   |   |   |
| "Chandigarh"           | 13.00  |   |   |   |
| "Santa Monica"         | 13.00  |   |   |   |
| "Wrexham"              | 13.00  |   |   |   |
| "The Dalles"           | 13.00  |   |   |   |
| "Asuncion"             | 13.00  |   |   |   |
| "LaFayette"            | 13.00  |   |   |   |
| "Akron"                | 13.00  |   |   |   |
| "Mexico City"          | 12.45  |   |   |   |
| "Detroit"              | 12.33  |   |   |   |
| "Washington"           | 12.18  |   |   |   |
| "Gurgaon"              | 11.83  |   |   |   |
| "Minato"               | 11.62  |   |   |   |
| "Osaka"                | 11.60  |   |   |   |
| "New Delhi"            | 11.44  |   |   |   |
| "Cambridge"            | 11.42  |   |   |   |
| "Kiev"                 | 11.29  |   |   |   |
| "Jaipur"               | 11.00  |   |   |   |
| "Ipoh"                 | 11.00  |   |   |   |
| "Zurich"               | 10.94  |   |   |   |
| "Istanbul"             | 10.53  |   |   |   |
| "Manila"               | 10.50  |   |   |   |
| "Bengaluru"            | 10.47  |   |   |   |
| "Stockholm"            | 10.25  |   |   |   |
| "Jakarta"              | 9.75   |   |   |   |
| "Taguig"               | 9.67   |   |   |   |
| "San Diego"            | 9.53   |   |   |   |
| "Burnaby"              | 9.50   |   |   |   |
| "Atlanta"              | 9.33   |   |   |   |
| "Kirkland"             | 9.13   |   |   |   |
| "South San Francisco"  | 8.67   |   |   |   |
| "Moscow"               | 7.67   |   |   |   |
| "Courbevoie"           | 7.50   |   |   |   |
| "Montevideo"           | 7.50   |   |   |   |
| "Yokohama"             | 7.25   |   |   |   |
| "St. Louis"            | 7.00   |   |   |   |
| "Medellin"             | 7.00   |   |   |   |
| "Thessaloniki"         | 7.00   |   |   |   |
| "Frankfurt"            | 7.00   |   |   |   |
| "East Lansing"         | 7.00   |   |   |   |
| "Fremont"              | 6.58   |   |   |   |
| "Oviedo"               | 6.50   |   |   |   |
| "Helsinki"             | 6.00   |   |   |   |
| "Nanded"               | 6.00   |   |   |   |
| "Kharagpur"            | 6.00   |   |   |   |
| "Bandung"              | 6.00   |   |   |   |
| "Tempe"                | 6.00   |   |   |   |
| "San Mateo"            | 5.50   |   |   |   |
| "Boulder"              | 5.33   |   |   |   |
| "Timisoara"            | 5.33   |   |   |   |
| "Denver"               | 5.33   |   |   |   |
| "Quezon City"          | 5.20   |   |   |   |
| "Jacksonville"         | 5.00   |   |   |   |
| "University Park"      | 5.00   |   |   |   |
| "Columbia"             | 5.00   |   |   |   |
| "Vienna"               | 4.75   |   |   |   |
| "Orlando"              | 4.50   |   |   |   |
| "Eau Claire"           | 4.13   |   |   |   |
| "Cluj-Napoca"          | 4.00   |   |   |   |
| "Doha"                 | 4.00   |   |   |   |
| "Richardson"           | 4.00   |   |   |   |
| "Culiacan"             | 4.00   |   |   |   |
| "Marseille"            | 4.00   |   |   |   |
| "Brussels"             | 4.00   |   |   |   |
| "Poznan"               | 4.00   |   |   |   |
| "Kharkiv"              | 4.00   |   |   |   |
| "Ashburn"              | 4.00   |   |   |   |
| "Portland"             | 3.80   |   |   |   |
| "Colombo"              | 3.50   |   |   |   |
| "Izmir"                | 3.50   |   |   |   |
| "Wellesley"            | 3.00   |   |   |   |
| "Norfolk"              | 3.00   |   |   |   |
| "Adelaide"             | 3.00   |   |   |   |
| "Petaling Jaya"        | 3.00   |   |   |   |
| "Madison"              | 3.00   |   |   |   |
| "Druid Hills"          | 3.00   |   |   |   |
| "Stanford"             | 3.00   |   |   |   |
| "Zagreb"               | 3.00   |   |   |   |
| "Milpitas"             | 2.57   |   |   |   |
| "Brisbane"             | 2.33   |   |   |   |
| "Las Vegas"            | 2.00   |   |   |   |
| "Jersey City"          | 2.00   |   |   |   |
| "Chico"                | 2.00   |   |   |   |
| "Salford"              | 2.00   |   |   |   |
| "Iasi"                 | 2.00   |   |   |   |
| "Maracaibo"            | 1.50   |   |   |   |
| "Council Bluffs"       | 1.50   |   |   |   |
| "Antwerp"              | 1.50   |   |   |   |
| "Vilnius"              | 1.00   |   |   |   |
| "Rosario"              | 1.00   |   |   |   |
| "Oslo"                 | 1.00   |   |   |   |
| "Edmonton"             | 1.00   |   |   |   |
| "Lahore"               | 1.00   |   |   |   |
| "Greer"                | 1.00   |   |   |   |
| "Patna"                | 1.00   |   |   |   |
| "Piscataway Township"  | 1.00   |   |   |   |
| "Villeneuve-d'Ascq"    | 1.00   |   |   |   |
| "Kansas City"          | 0.67   |   |   |   |
| "Fortaleza"            | 0.00   |   |   |   |
| "Coventry"             | 0.00   |   |   |   |
| "Nagoya"               | 0.00   |   |   |   |
| "South El Monte"       | 0.00   |   |   |   |
| "Panama City"          | 0.00   |   |   |   |
| "Auckland"             | 0.00   |   |   |   |
| "Forest Park"          | 0.00   |   |   |   |
| "Lucknow"              | 0.00   |   |   |   |
| "Makati"               | 0.00   |   |   |   |
| "Indianapolis"         | 0.00   |   |   |   |
| "Hayward"              | 0.00   |   |   |   |
| "Waterloo"             | 0.00   |   |   |   |
| "St. John's"           | 0.00   |   |   |   |
| "Manchester"           | 0.00   |   |   |   |
| "Karachi"              | 0.00   |   |   |   |
| "Tampa"                | 0.00   |   |   |   |
| "San Salvador"         | 0.00   |   |   |   |
| "Shibuya"              | 0.00   |   |   |   |
| "Bratislava"           | 0.00   |   |   |   |
| "Goose Creek"          | 0.00   |   |   |   |
| "Westlake Village"     | 0.00   |   |   |   |
| "Pleasanton"           | 0.00   |   |   |   |
| "Beijing"              | 0.00   |   |   |   |
| "Marlboro"             | 0.00   |   |   |   |
| "Minneapolis"          | 0.00   |   |   |   |
| "Chuo"                 | 0.00   |   |   |   |
| "Nairobi"              | 0.00   |   |   |   |


**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


### SQL Queries:

  SELECT country, MAX(v2_product_category) AS most_common_product_type
  FROM all_sessions
  GROUP BY country;

  SELECT city, MAX(v2_product_category) AS most_common_product_type
  FROM all_sessions
  GROUP BY city;



### Answer:

| Country                | product categories                    |
|------------------------|---------------------------------------|
| "Bangladesh"           | "Home/Shop by Brand/YouTube/"         |
| "Indonesia"            | "Home/Shop by Brand/YouTube/"         |
| "Venezuela"            | "Home/Shop by Brand/YouTube/"         |
| "Luxembourg"           | NULL                                  |
| "Sweden"               | "Home/Shop by Brand/YouTube/"         |
| "Montenegro"           | "Home/Shop by Brand/YouTube/"         |
| "Uganda"               | "Home/Shop by Brand/Google/"          |
| "Jordan"               | "Home/Office/"                        |
| "Dominican Republic"   | "Home/Shop by Brand/YouTube/"         |
| "Cambodia"             | "Home/Shop by Brand/YouTube/"         |
| "Ireland"              | "Home/Shop by Brand/YouTube/"         |
| "Papua New Guinea"     | "Home/Shop by Brand/YouTube/"         |
| "Singapore"            | "Home/Shop by Brand/YouTube/"         |
| "Laos"                 | "Home/Shop by Brand/YouTube/"         |
| "San Marino"           | "Home/Shop by Brand/YouTube/"         |
| "Sri Lanka"            | "Home/Shop by Brand/YouTube/"         |
| "Brunei"               | "Home/Shop by Brand/YouTube/"         |
| "N/A"                  | "Home/Shop by Brand/YouTube/"         |
| "Portugal"             | "Home/Shop by Brand/YouTube/"         |
| "Finland"              | "Home/Shop by Brand/Google/"          |
| "Malta"                | "Home/Shop by Brand/YouTube/"         |
| "Colombia"             | "Home/Shop by Brand/YouTube/"         |
| "Albania"              | "Home/Shop by Brand/YouTube/"         |
| "Saudi Arabia"         | "Home/Shop by Brand/YouTube/"         |
| "Ukraine"              | "Home/Shop by Brand/YouTube/"         |
| "Macau"                | "Home/Shop by Brand/Google/"          |
| "Latvia"               | "Home/Shop by Brand/YouTube/"         |
| "Kyrgyzstan"           | "Home/Electronics/"                   |
| "Algeria"              | "Home/Shop by Brand/YouTube/"         |
| "France"               | "Home/Shop by Brand/YouTube/"         |
| "Réunion"              | "Home/Shop by Brand/YouTube/"         |
| "Maldives"             | "Home/Apparel/Men's/Men's-Outerwear/" |
| "Slovakia"             | "Home/Shop by Brand/YouTube/"         |
| "Israel"               | "Home/Shop by Brand/YouTube/"         |
| "Ghana"                | "Home/Shop by Brand/YouTube/"         |
| "Malaysia"             | "Home/Shop by Brand/YouTube/"         |
| "Kenya"                | "Home/Electronics/"                   |
| "Iceland"              | "Home/Office/"                        |
| "Kuwait"               | "Home/Shop by Brand/YouTube/"         |
| "Hong Kong"            | "Home/Shop by Brand/YouTube/"         |
| "Philippines"          | "Lifestyle/"                          |
| "United States"        | "Wearables/Men's T-Shirts/"           |
| "Cyprus"               | "Home/Shop by Brand/YouTube/"         |
| "Turkey"               | "Home/Shop by Brand/YouTube/"         |
| "Nigeria"              | "Home/Shop by Brand/YouTube/"         |
| "Rwanda"               | "Home/Shop by Brand/YouTube/"         |
| "Zimbabwe"             | "Home/Electronics/"                   |
| "China"                | "Home/Shop by Brand/YouTube/"         |
| "Armenia"              | "Home/Accessories/"                   |
| "Belarus"              | "Home/Shop by Brand/YouTube/"         |
| "Qatar"                | "Home/Office/"                        |
| "Netherlands"          | "Wearables/Men's T-Shirts/"           |
| "Paraguay"             | "Home/Apparel/Men's/Men's-T-Shirts/"  |
| "Martinique"           | "Home/Shop by Brand/YouTube/"         |
| "Australia"            | "Nest-USA"                            |
| "Mauritius"            | "Home/Shop by Brand/YouTube/"         |
| "Serbia"               | "Home/Shop by Brand/YouTube/"         |
| "Côte d’Ivoire"        | "Home/Shop by Brand/YouTube/"         |
| "Bosnia & Herzegovina" | "Home/Shop by Brand/YouTube/"         |
| "Macedonia (FYROM)"    | "Home/Office/"                        |
| "Bahrain"              | "Home/Shop by Brand/YouTube/"         |
| "Spain"                | "Home/Shop by Brand/YouTube/"         |
| "United Arab Emirates" | "Home/Shop by Brand/YouTube/"         |
| "Georgia"              | "Home/Shop by Brand/YouTube/"         |
| "Belgium"              | "YouTube"                             |
| "Taiwan"               | "Wearables/Men's T-Shirts/"           |
| "Thailand"             | "Home/Shop by Brand/YouTube/"         |
| "El Salvador"          | "Home/Shop by Brand/YouTube/"         |
| "Italy"                | "Home/Shop by Brand/YouTube/"         |
| "Uruguay"              | "Home/Shop by Brand/YouTube/"         |
| "Oman"                 | "Home/Shop by Brand/YouTube/"         |
| "United Kingdom"       | "Home/Spring Sale!/"                  |
| "Germany"              | "Home/Shop by Brand/YouTube/"         |
| "Canada"               | "Home/Shop by Brand/YouTube/"         |
| "South Korea"          | "Home/Shop by Brand/YouTube/"         |
| "Barbados"             | "Home/Electronics/"                   |
| "Sint Maarten"         | "Home/Shop by Brand/Google/"          |
| "Argentina"            | "Home/Shop by Brand/YouTube/"         |
| "Slovenia"             | "Home/Shop by Brand/YouTube/"         |
| "Egypt"                | "Home/Shop by Brand/YouTube/"         |
| "Greece"               | "Home/Shop by Brand/YouTube/"         |
| "Bahamas"              | "Home/Shop by Brand/YouTube/"         |
| "Puerto Rico"          | "Home/Shop by Brand/Google/"          |
| "India"                | "Home/Shop by Brand/YouTube/"         |
| "French Polynesia"     | "Home/Shop by Brand/YouTube/"         |
| "Chile"                | "Home/Shop by Brand/YouTube/"         |
| "Estonia"              | "Home/Shop by Brand/YouTube/"         |
| "Vietnam"              | "Home/Shop by Brand/YouTube/"         |
| "South Africa"         | "Home/Shop by Brand/YouTube/"         |
| "Peru"                 | "Home/Shop by Brand/YouTube/"         |
| "Kazakhstan"           | "Home/Shop by Brand/YouTube/"         |
| "Kosovo"               | "Home/Shop by Brand/Google/"          |
| "Japan"                | "Wearables/Men's T-Shirts/"           |
| "Denmark"              | "Home/Shop by Brand/YouTube/"         |
| "Jamaica"              | "Home/Apparel/Men's/Men's-Outerwear/" |
| "Iraq"                 | "Home/Shop by Brand/YouTube/"         |
| "Switzerland"          | "Home/Shop by Brand/YouTube/"         |
| "Ecuador"              | "Home/Shop by Brand/YouTube/"         |
| "New Zealand"          | "Home/Shop by Brand/YouTube/"         |
| "Hungary"              | "Home/Shop by Brand/YouTube/"         |
| "Russia"               | "Home/Shop by Brand/YouTube/"         |
| "Belize"               | "Home/Drinkware/"                     |
| "Honduras"             | "Home/Shop by Brand/YouTube/"         |
| "Norway"               | "Home/Shop by Brand/YouTube/"         |
| "Botswana"             | "Home/Bags/"                          |
| "Pakistan"             | "Home/Shop by Brand/YouTube/"         |
| "Romania"              | "Home/Shop by Brand/YouTube/"         |
| "Brazil"               | "Home/Shop by Brand/YouTube/"         |
| "Trinidad & Tobago"    | "Home/Shop by Brand/YouTube/"         |
| "Austria"              | "Home/Shop by Brand/YouTube/"         |
| "Guatemala"            | "Home/Shop by Brand/YouTube/"         |
| "Bolivia"              | "Home/Shop by Brand/Google/"          |
| "Ethiopia"             | "Home/Shop by Brand/YouTube/"         |
| "Panama"               | "Home/Shop by Brand/YouTube/"         |
| "Lithuania"            | "Home/Shop by Brand/YouTube/"         |
| "Bulgaria"             | "Wearables/Men's T-Shirts/"           |
| "Croatia"              | "Home/Shop by Brand/YouTube/"         |
| "Tunisia"              | "Home/Shop by Brand/YouTube/"         |
| "Sudan"                | "Home/Shop by Brand/YouTube/"         |
| "Mali"                 | "Home/Shop by Brand/YouTube/"         |
| "Morocco"              | "Home/Shop by Brand/YouTube/"         |
| "Moldova"              | "Home/Shop by Brand/YouTube/"         |
| "Nicaragua"            | "Home/Office/"                        |
| "Mexico"               | "Home/Shop by Brand/YouTube/"         |
| "Nepal"                | "Home/Shop by Brand/YouTube/"         |
| "Tanzania"             | "Home/Shop by Brand/YouTube/"         |
| "Palestine"            | "Home/Bags/"                          |
| "Poland"               | "Home/Shop by Brand/YouTube/"         |
| "Lebanon"              | "Home/Shop by Brand/YouTube/"         |
| "Costa Rica"           | "Home/Office/"                        |
| "Jersey"               | "Home/Apparel/Men's/Men's-Outerwear/" |
| "Gibraltar"            | "Home/Shop by Brand/YouTube/"         |
| "Haiti"                | "Home/Apparel/Men's/Men's-T-Shirts/"  |
| "Czechia"              | "Home/Shop by Brand/YouTube/"         |
| "Somalia"              | "Home/Apparel/Men's/Men's-T-Shirts/"  |
| "Myanmar (Burma)"      | "Home/Shop by Brand/YouTube/"         |

| City                    | product categories                               |
|-------------------------|--------------------------------------------------|
| "Norfolk"               | "Home/Shop by Brand/"                            |
| "Taguig"                | "Home/Shop by Brand/YouTube/"                    |
| "Kharagpur"             | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "South San Francisco"   | "Home/Bags/Backpacks/"                           |
| "Sherbrooke"            | "Home/Nest/Nest-USA/"                            |
| "Izmir"                 | "Home/Apparel/"                                  |
| "Riyadh"                | "Home/Office/"                                   |
| "Auckland"              | "Home/Shop by Brand/Google/"                     |
| "Austin"                | "Home/Shop by Brand/YouTube/"                    |
| "Panama City"           | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "Fort Worth"            | "Home/Shop by Brand/YouTube/"                    |
| "Stuttgart"             | "Home/Electronics/Audio/"                        |
| "Petaling Jaya"         | "Home/Apparel/Women's/Women's-Performance Wear/" |
| "Singapore"             | "Home/Shop by Brand/YouTube/"                    |
| "Belgrade"              | "Home/Drinkware/"                                |
| "Hanoi"                 | "Home/Shop by Brand/YouTube/"                    |
| "Manila"                | "Home/Drinkware/"                                |
| "Quezon City"           | "Lifestyle/"                                     |
| "LaFayette"             | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Washington"            | "Home/Shop by Brand/YouTube/"                    |
| "Gurgaon"               | "Home/Shop by Brand/YouTube/"                    |
| "Bhubaneswar"           | "Home/Accessories/Drinkware/"                    |
| "Antwerp"               | "Home/Office/"                                   |
| "Wroclaw"               | "Home/Electronics/"                              |
| "Montreal"              | "Home/Shop by Brand/YouTube/"                    |
| "Fremont"               | "Home/Shop by Brand/Google/"                     |
| "Quimper"               | "Home/Electronics/Audio/"                        |
| "Vladivostok"           | "Home/Limited Supply/Bags/"                      |
| "Chiyoda"               | "Home/Shop by Brand/YouTube/"                    |
| "Longtan District"      | "Home/Accessories/Drinkware/"                    |
| "Brussels"              | "(not set)"                                      |
| "Cupertino"             | "Home/Shop by Brand/YouTube/"                    |
| "Maracaibo"             | "Home/Fruit Games/"                              |
| "East Lansing"          | "Home/Bags/Backpacks/"                           |
| "Bellingham"            | "Home/Nest/Nest-USA/"                            |
| "Kuala Lumpur"          | "Home/Shop by Brand/YouTube/"                    |
| "Santa Monica"          | "Home/Bags/"                                     |
| "Kiev"                  | "Home/Shop by Brand/YouTube/"                    |
| "Budapest"              | "Home/Shop by Brand/YouTube/"                    |
| "Zagreb"                | "Home/Shop by Brand/YouTube/"                    |
| "University Park"       | "Home/Bags/Backpacks/"                           |
| "Mississauga"           | "Home/Shop by Brand/YouTube/"                    |
| "Villeneuve-d'Ascq"     | "Home/Shop by Brand/Google/"                     |
| "Colombo"               | "Home/Shop by Brand/Android/"                    |
| "Indore"                | "Home/Shop by Brand/YouTube/"                    |
| "Orlando"               | "Home/Shop by Brand/YouTube/"                    |
| "Stockholm"             | "Home/Shop by Brand/YouTube/"                    |
| "Pune"                  | "Home/Shop by Brand/YouTube/"                    |
| "Bangkok"               | "Home/Shop by Brand/YouTube/"                    |
| "Moscow"                | "Home/Shop by Brand/YouTube/"                    |
| "Neipu Township"        | "Home/Apparel/Women's/Women's-Outerwear/"        |
| "Calgary"               | "Home/Shop by Brand/YouTube/"                    |
| "Wrexham"               | "Home/Shop by Brand/"                            |
| "Cluj-Napoca"           | "Home/Apparel/"                                  |
| "San Antonio"           | "Home/Shop by Brand/YouTube/"                    |
| "Nice"                  | "Home/Drinkware/"                                |
| "Coventry"              | "Home/Shop by Brand/YouTube/"                    |
| "Cape Town"             | "Home/Apparel/Men's/"                            |
| "Courbevoie"            | "Home/Shop by Brand/"                            |
| "Egham"                 | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Zhongli District"      | "Home/Shop by Brand/YouTube/"                    |
| "Vancouver"             | "Home/Shop by Brand/YouTube/"                    |
| "Esbjerg"               | "Home/Apparel/Women's/Women's-T-Shirts/"         |
| "Santiago"              | "Home/Office/"                                   |
| "Jersey City"           | "Home/Bags/Backpacks/"                           |
| "Berkeley"              | "Home/Apparel/Kid's/Kid's-Infant/"               |
| "Copenhagen"            | "Home/Apparel/Headgear/"                         |
| "Oslo"                  | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Frankfurt"             | "Home/Shop by Brand/Google/"                     |
| "San Jose"              | "Home/Spring Sale!/"                             |
| "Cambridge"             | "Home/Shop by Brand/Google/"                     |
| "Rio de Janeiro"        | "Home/Shop by Brand/Google/"                     |
| "Salem"                 | "Home/Shop by Brand/YouTube/"                    |
| "Tel Aviv-Yafo"         | "Home/Shop by Brand/YouTube/"                    |
| "Perth"                 | "Home/Shop by Brand/YouTube/"                    |
| "Hayward"               | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Jaipur"                | "Home/Shop by Brand/YouTube/"                    |
| "Charlottetown"         | "Home/Office/"                                   |
| "Cork"                  | "Home/Accessories/Stickers/"                     |
| "Columbia"              | "Home/Electronics/"                              |
| "New York"              | "Lifestyle/"                                     |
| "Greer"                 | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "San Francisco"         | "Nest-USA"                                       |
| "Makati"                | "Home/Electronics/Audio/"                        |
| "Berlin"                | "Home/Shop by Brand/YouTube/"                    |
| "Dallas"                | "Home/Shop by Brand/YouTube/"                    |
| "Jacksonville"          | "Home/Electronics/Electronics Accessories/"      |
| "Chuo"                  | "Home/Apparel/Women's/"                          |
| "Krakow"                | "Home/Drinkware/"                                |
| "Barcelona"             | "Home/Shop by Brand/YouTube/"                    |
| "Warsaw"                | "Home/Shop by Brand/YouTube/"                    |
| "Edmonton"              | "Home/Shop by Brand/YouTube/"                    |
| "Rosario"               | "Home/Apparel/Men's/"                            |
| "Shibuya"               | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Pittsburgh"            | "Home/Office/Notebooks & Journals/"              |
| "Jakarta"               | "Home/Shop by Brand/YouTube/"                    |
| "Boston"                | "Home/Shop by Brand/YouTube/"                    |
| "Burnaby"               | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Rexburg"               | "Home/Drinkware/"                                |
| "Ashburn"               | "Home/Lifestyle/Fun/"                            |
| "Ipoh"                  | "Home/Accessories/Housewares/"                   |
| "Patna"                 | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "London"                | "Home/Shop by Brand/YouTube/"                    |
| "Doha"                  | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Rotterdam"             | "Home/Apparel/Headgear/"                         |
| "Bellflower"            | "Home/Shop by Brand/YouTube/"                    |
| "Philadelphia"          | "Home/Shop by Brand/YouTube/"                    |
| "Hyderabad"             | "Home/Shop by Brand/YouTube/"                    |
| "Athens"                | "Home/Shop by Brand/YouTube/"                    |
| "Parsippany-Troy Hills" | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "Pozuelo de Alarcon"    | "Home/Shop by Brand/YouTube/"                    |
| "Medellin"              | "Home/Drinkware/"                                |
| "Glasgow"               | "Home/Electronics/Audio/"                        |
| "Monterrey"             | "Home/Office/"                                   |
| "San Diego"             | "Home/Shop by Brand/YouTube/"                    |
| "Madison"               | "Home/Bags/"                                     |
| "Council Bluffs"        | "Home/Apparel/"                                  |
| "Amsterdam"             | "Home/Shop by Brand/YouTube/"                    |
| "Osaka"                 | "Home/Shop by Brand/Google/"                     |
| "Lucknow"               | "Home/Shop by Brand/YouTube/"                    |
| "Karachi"               | "Home/Shop by Brand/YouTube/"                    |
| "Kolkata"               | "Home/Shop by Brand/YouTube/"                    |
| "Bogota"                | "Home/Shop by Brand/YouTube/"                    |
| "Wellesley"             | "Home/Office/Writing Instruments/"               |
| "Dublin"                | "Home/Shop by Brand/YouTube/"                    |
| "Palo Alto"             | "Nest-USA"                                       |
| "Iasi"                  | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "La Victoria"           | "Home/Shop by Brand/YouTube/"                    |
| "San Mateo"             | "Home/Clearance Sale/"                           |
| "Buenos Aires"          | "Home/Shop by Brand/YouTube/"                    |
| "Sandton"               | "Home/Electronics/"                              |
| "Las Vegas"             | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "Belo Horizonte"        | "Home/Bags/Shopping and Totes/"                  |
| "Odessa"                | "Home/Accessories/Drinkware/"                    |
| "Pleasanton"            | "Home/Bags/"                                     |
| "Saint Petersburg"      | "Home/Shop by Brand/YouTube/"                    |
| "Sydney"                | "Nest-USA"                                       |
| "Kalamazoo"             | "(not set)"                                      |
| "Vilnius"               | "Home/Apparel/Men's/"                            |
| "Thessaloniki"          | "Home/Shop by Brand/"                            |
| "Vienna"                | "Home/Shop by Brand/YouTube/"                    |
| "Brisbane"              | "Home/Shop by Brand/YouTube/"                    |
| "Rome"                  | "Home/Shop by Brand/YouTube/"                    |
| "St. Louis"             | "Home/Shop by Brand/"                            |
| "Salford"               | "Home/Electronics/Electronics Accessories/"      |
| "Oviedo"                | "Home/Apparel/"                                  |
| "Santa Clara"           | "Home/Shop by Brand/Google/"                     |
| "Chicago"               | "Nest-USA"                                       |
| "Antalya"               | "(not set)"                                      |
| "Brno"                  | "Home/Office/Notebooks & Journals/"              |
| "Bucharest"             | "Home/Shop by Brand/YouTube/"                    |
| "Houston"               | "Home/Shop by Brand/YouTube/"                    |
| "N/A"                   | "YouTube"                                        |
| "Portland"              | "Home/Shop by Brand/YouTube/"                    |
| "Ghent"                 | "Home/Accessories/"                              |
| "Menlo Park"            | "Home/Shop by Brand/Google/"                     |
| "El Paso"               | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Lisbon"                | "Home/Apparel/Headgear/"                         |
| "Marlboro"              | "(not set)"                                      |
| "San Bruno"             | "Home/Shop by Brand/YouTube/"                    |
| "Eau Claire"            | "Home/Shop by Brand/Google/"                     |
| "St. John's"            | "Home/Electronics/Power/"                        |
| "Waterloo"              | "Home/Apparel/"                                  |
| "Seattle"               | "Home/Shop by Brand/YouTube/"                    |
| "Sapporo"               | "Home/Apparel/"                                  |
| "Columbus"              | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "Indianapolis"          | "Home/Office/Writing Instruments/"               |
| "Helsinki"              | "(not set)"                                      |
| "Sao Paulo"             | "Home/Shop by Brand/YouTube/"                    |
| "Hong Kong"             | "Home/Shop by Brand/YouTube/"                    |
| "Westville"             | "Home/Bags/"                                     |
| "Marseille"             | "Home/Shop by Brand/YouTube/"                    |
| "Montreuil"             | "Home/Office/"                                   |
| "Melbourne"             | "Home/Shop by Brand/YouTube/"                    |
| "South El Monte"        | "Home/Apparel/Men's/"                            |
| "Piscataway Township"   | "Home/Apparel/Men's/"                            |
| "Kitchener"             | "Home/Electronics/Audio/"                        |
| "Lahore"                | "Home/Electronics/"                              |
| "Johnson City"          | "Home/Shop by Brand/Google/"                     |
| "Milan"                 | "Home/Shop by Brand/YouTube/"                    |
| "Chico"                 | "Home/Shop by Brand/YouTube/"                    |
| "Poznan"                | "Home/Office/Notebooks & Journals/"              |
| "Amã"                   | "Home/Bags/"                                     |
| "Fortaleza"             | "Home/Shop by Brand/Android/"                    |
| "Mumbai"                | "Home/Shop by Brand/YouTube/"                    |
| "Nairobi"               | "Home/Electronics/"                              |
| "Raleigh"               | "Home/Apparel/Kid's/Kid's-Infant/"               |
| "Alexandria"            | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Adelaide"              | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "Los Angeles"           | "Home/Spring Sale!/"                             |
| "Ann Arbor"             | "Home/Shop by Brand/YouTube/"                    |
| "Minneapolis"           | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Istanbul"              | "Home/Shop by Brand/YouTube/"                    |
| "Culiacan"              | "Home/Drinkware/"                                |
| "Nanded"                | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Redmond"               | "Home/Shop by Brand/YouTube/"                    |
| "Westlake Village"      | "(not set)"                                      |
| "Oxford"                | "Home/Electronics/Audio/"                        |
| "Redwood City"          | "Home/Nest/Nest-USA/"                            |
| "Appleton"              | "Home/Electronics/"                              |
| "Bratislava"            | "(not set)"                                      |
| "The Dalles"            | "Home/Electronics/"                              |
| "Timisoara"             | "Home/Shop by Brand/Android/"                    |
| "Mexico City"           | "Home/Shop by Brand/YouTube/"                    |
| "Druid Hills"           | "Home/Office/"                                   |
| "Paris"                 | "Home/Shop by Brand/YouTube/"                    |
| "Gothenburg"            | "Home/Apparel/Women's/Women's-Performance Wear/" |
| "Kovrov"                | "Home/Shop by Brand/Google/"                     |
| "Skopje"                | "Home/Office/"                                   |
| "Asuncion"              | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Phoenix"               | "Home/Office/"                                   |
| "Bilbao"                | "Home/Apparel/"                                  |
| "Boulder"               | "Home/Lifestyle/"                                |
| "Ottawa"                | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Stanford"              | "Home/Apparel/Men's/"                            |
| "Mountain View"         | "Waze"                                           |
| "San Salvador"          | "Home/Electronics/Electronics Accessories/"      |
| "Detroit"               | "Home/Shop by Brand/Google/"                     |
| "Minato"                | "Home/Shop by Brand/YouTube/"                    |
| "Manchester"            | "Home/Shop by Brand/YouTube/"                    |
| "Bengaluru"             | "Home/Shop by Brand/YouTube/"                    |
| "Montevideo"            | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Richardson"            | "Home/Electronics/Audio/"                        |
| "Tampa"                 | "(not set)"                                      |
| "Sunnyvale"             | "Nest-USA"                                       |
| "Avon"                  | "Home/Apparel/Headgear/"                         |
| "Sacramento"            | "Home/Apparel/"                                  |
| "New Delhi"             | "Home/Shop by Brand/YouTube/"                    |
| "Kansas City"           | "Home/Drinkware/"                                |
| "Watford"               | "Home/Shop by Brand/YouTube/"                    |
| "Chennai"               | "Home/Shop by Brand/YouTube/"                    |
| "Santa Fe"              | "Home/Electronics/Electronics Accessories/"      |
| "Kirkland"              | "Home/Shop by Brand/Google/"                     |
| "Goose Creek"           | "Home/Apparel/Headgear/"                         |
| "Dubai"                 | "Home/Shop by Brand/YouTube/"                    |
| "Irvine"                | "Home/Shop by Brand/"                            |
| "Bandung"               | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Akron"                 | "Home/Apparel/Men's/"                            |
| "Nashville"             | "Nest-USA"                                       |
| "Beijing"               | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "Hamburg"               | "Home/Shop by Brand/YouTube/"                    |
| "Milpitas"              | "Home/Shop by Brand/Google/"                     |
| "Prague"                | "Home/Shop by Brand/YouTube/"                    |
| "Oakland"               | "Home/Shop by Brand/Google/"                     |
| "Shinjuku"              | "Home/Office/"                                   |
| "Munich"                | "Home/Shop by Brand/YouTube/"                    |
| "Zurich"                | "Home/Shop by Brand/YouTube/"                    |
| "Sakai"                 | "Home/Office/Notebooks & Journals/"              |
| "Denver"                | "Home/Electronics/"                              |
| "Yokohama"              | "Home/Shop by Brand/Google/"                     |
| "Nagoya"                | "Home/Shop by Brand/Google/"                     |
| "Charlotte"             | "Home/Shop by Brand/YouTube/"                    |
| "Madrid"                | "Home/Shop by Brand/YouTube/"                    |
| "Ho Chi Minh City"      | "Home/Shop by Brand/YouTube/"                    |
| "Forest Park"           | "Home/Apparel/Men's/Men's-Outerwear/"            |
| "Ahmedabad"             | "Home/Shop by Brand/YouTube/"                    |
| "Toronto"               | "Home/Shop by Brand/YouTube/"                    |
| "Chandigarh"            | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Kharkiv"               | "Home/Office/"                                   |
| "Bordeaux"              | "Home/Accessories/Housewares/"                   |
| "Quebec City"           | "Home/Shop by Brand/YouTube/"                    |
| "Atlanta"               | "Home/Shop by Brand/YouTube/"                    |
| "Seoul"                 | "Home/Shop by Brand/YouTube/"                    |
| "Tempe"                 | "Home/Apparel/Men's/Men's-T-Shirts/"             |
| "Lake Oswego"           | "Home/Apparel/Women's/Women's-Performance Wear/" |



**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


### SQL Queries: 

  SELECT country, v2_product_name, COUNT(*) AS item_count
  FROM all_sessions
  GROUP BY country, v2_product_name
  order by item_count desc;

  SELECT city, v2_product_name, COUNT(*) AS item_count
  FROM all_sessions
  WHERE city NOT IN ('N/A')
  GROUP BY city, v2_product_name
  order by item_count desc;


### Answer:

| Country                 | Top Selling Product                                    |Volume|
|-------------------------|--------------------------------------------------------|-----|
| "United States"         | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 169 |
| "India"                 | "YouTube Custom Decals"                                | 22  |
| "United Kingdom"        | "22 oz YouTube Bottle Infuser"                         | 22  |
| "Canada"                | "22 oz YouTube Bottle Infuser"                         | 13  |
| "Germany"               | "YouTube Twill Cap"                                    | 13  |
| "France"                | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 8   |
| "Australia"             | "22 oz YouTube Bottle Infuser"                         | 8   |
| "Japan"                 | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 7   |
| "Indonesia"             | "22 oz YouTube Bottle Infuser"                         | 6   |
| "Brazil"                | "Google Men's Vintage Badge Tee Black"                 | 6   |
| "Taiwan"                | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 6   |
| "Czechia"               | "YouTube Hard Cover Journal"                           | 6   |
| "Taiwan"                | "Sport Bag"                                            | 5   |
| "Czechia"               | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 5   |
| "Italy"                 | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 5   |
| "Singapore"             | "Google Men's 100% Cotton Short Sleeve Hero Tee Black" | 5   |
| "Denmark"               | "YouTube Hard Cover Journal"                           | 5   |
| "Mexico"                | "YouTube Men's Short Sleeve Hero Tee Black"            | 5   |
| "Netherlands"           | "YouTube Twill Cap"                                    | 5   |
| "Romania"               | "YouTube Custom Decals"                                | 5   |
| "Ireland"               | "24 oz YouTube Sergeant Stripe Bottle"                 | 4   |
| "Spain"                 | "YouTube Men's Short Sleeve Hero Tee White"            | 4   |
| "Thailand"              | "YouTube Men's Vintage Henley"                         | 4   |
| "Turkey"                | "YouTube Hard Cover Journal"                           | 4   |
| "Russia"                | "Google Women's Fleece Hoodie"                         | 4   |
| "Colombia"              | "22 oz YouTube Bottle Infuser"                         | 4   |
| "Spain"                 | "22 oz YouTube Bottle Infuser"                         | 4   |
| "Pakistan"              | "22 oz YouTube Bottle Infuser"                         | 4   |
| "Philippines"           | "YouTube Notebook and Pen Set"                         | 3   |
| "Georgia"               | "YouTube Custom Decals"                                | 3   |
| "Switzerland"           | "Google G Noise-reducing Bluetooth Headphones"         | 3   |
| "Belgium"               | "YouTube Trucker Hat"                                  | 3   |
| "Greece"                | "22 oz YouTube Bottle Infuser"                         | 3   |
| "Ukraine"               | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 3   |
| "Mexico"                | "YouTube RFID Journal"                                 | 3   |
| "Malaysia"              | "Google Men's Short Sleeve Hero Tee Heather"           | 3   |
| "Israel"                | "Nest® Protect Smoke + CO Black Wired Alarm-USA"       | 3   |
| "Argentina"             | "Google Alpine Style Backpack"                         | 3   |
| "Sweden"                | "YouTube Men's Short Sleeve Hero Tee White"            | 3   |
| "New Zealand"           | "YouTube RFID Journal"                                 | 3   |
| "Indonesia"             | "YouTube Men's Short Sleeve Hero Tee Charcoal"         | 3   |
| "Poland"                | "YouTube Men's Vintage Tank"                           | 3   |
| "Villeneuve-d'Ascq"     | "Home/Shop by Brand/Google/"                           |     |
| "Colombo"               | "Home/Shop by Brand/Android/"                          |     |
| "Indore"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Orlando"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Stockholm"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Pune"                  | "Home/Shop by Brand/YouTube/"                          |     |
| "Bangkok"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Moscow"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Neipu Township"        | "Home/Apparel/Women's/Women's-Outerwear/"              |     |
| "Calgary"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Wrexham"               | "Home/Shop by Brand/"                                  |     |
| "Cluj-Napoca"           | "Home/Apparel/"                                        |     |
| "San Antonio"           | "Home/Shop by Brand/YouTube/"                          |     |
| "Nice"                  | "Home/Drinkware/"                                      |     |
| "Coventry"              | "Home/Shop by Brand/YouTube/"                          |     |
| "Cape Town"             | "Home/Apparel/Men's/"                                  |     |
| "Courbevoie"            | "Home/Shop by Brand/"                                  |     |
| "Egham"                 | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Zhongli District"      | "Home/Shop by Brand/YouTube/"                          |     |
| "Vancouver"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Esbjerg"               | "Home/Apparel/Women's/Women's-T-Shirts/"               |     |
| "Santiago"              | "Home/Office/"                                         |     |
| "Jersey City"           | "Home/Bags/Backpacks/"                                 |     |
| "Berkeley"              | "Home/Apparel/Kid's/Kid's-Infant/"                     |     |
| "Copenhagen"            | "Home/Apparel/Headgear/"                               |     |
| "Oslo"                  | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Frankfurt"             | "Home/Shop by Brand/Google/"                           |     |
| "San Jose"              | "Home/Spring Sale!/"                                   |     |
| "Cambridge"             | "Home/Shop by Brand/Google/"                           |     |
| "Rio de Janeiro"        | "Home/Shop by Brand/Google/"                           |     |
| "Salem"                 | "Home/Shop by Brand/YouTube/"                          |     |
| "Tel Aviv-Yafo"         | "Home/Shop by Brand/YouTube/"                          |     |
| "Perth"                 | "Home/Shop by Brand/YouTube/"                          |     |
| "Hayward"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Jaipur"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Charlottetown"         | "Home/Office/"                                         |     |
| "Cork"                  | "Home/Accessories/Stickers/"                           |     |
| "Columbia"              | "Home/Electronics/"                                    |     |
| "New York"              | "Lifestyle/"                                           |     |
| "Greer"                 | "Home/Apparel/Men's/Men's-Outerwear/"                  |     |
| "San Francisco"         | "Nest-USA"                                             |     |
| "Makati"                | "Home/Electronics/Audio/"                              |     |
| "Berlin"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Dallas"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Jacksonville"          | "Home/Electronics/Electronics Accessories/"            |     |
| "Chuo"                  | "Home/Apparel/Women's/"                                |     |
| "Krakow"                | "Home/Drinkware/"                                      |     |
| "Barcelona"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Warsaw"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Edmonton"              | "Home/Shop by Brand/YouTube/"                          |     |
| "Rosario"               | "Home/Apparel/Men's/"                                  |     |
| "Shibuya"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Pittsburgh"            | "Home/Office/Notebooks & Journals/"                    |     |
| "Jakarta"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Boston"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Burnaby"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Rexburg"               | "Home/Drinkware/"                                      |     |
| "Ashburn"               | "Home/Lifestyle/Fun/"                                  |     |
| "Ipoh"                  | "Home/Accessories/Housewares/"                         |     |
| "Patna"                 | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "London"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Doha"                  | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Rotterdam"             | "Home/Apparel/Headgear/"                               |     |
| "Bellflower"            | "Home/Shop by Brand/YouTube/"                          |     |
| "Philadelphia"          | "Home/Shop by Brand/YouTube/"                          |     |
| "Hyderabad"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Athens"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Parsippany-Troy Hills" | "Home/Apparel/Men's/Men's-Outerwear/"                  |     |
| "Pozuelo de Alarcon"    | "Home/Shop by Brand/YouTube/"                          |     |
| "Medellin"              | "Home/Drinkware/"                                      |     |
| "Glasgow"               | "Home/Electronics/Audio/"                              |     |
| "Monterrey"             | "Home/Office/"                                         |     |
| "San Diego"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Madison"               | "Home/Bags/"                                           |     |
| "Council Bluffs"        | "Home/Apparel/"                                        |     |
| "Amsterdam"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Osaka"                 | "Home/Shop by Brand/Google/"                           |     |
| "Lucknow"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Karachi"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Kolkata"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Bogota"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Wellesley"             | "Home/Office/Writing Instruments/"                     |     |
| "Dublin"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Palo Alto"             | "Nest-USA"                                             |     |
| "Iasi"                  | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "La Victoria"           | "Home/Shop by Brand/YouTube/"                          |     |
| "San Mateo"             | "Home/Clearance Sale/"                                 |     |
| "Buenos Aires"          | "Home/Shop by Brand/YouTube/"                          |     |
| "Sandton"               | "Home/Electronics/"                                    |     |
| "Las Vegas"             | "Home/Apparel/Men's/Men's-Outerwear/"                  |     |
| "Belo Horizonte"        | "Home/Bags/Shopping and Totes/"                        |     |
| "Odessa"                | "Home/Accessories/Drinkware/"                          |     |
| "Pleasanton"            | "Home/Bags/"                                           |     |
| "Saint Petersburg"      | "Home/Shop by Brand/YouTube/"                          |     |
| "Sydney"                | "Nest-USA"                                             |     |
| "Kalamazoo"             | "(not set)"                                            |     |
| "Vilnius"               | "Home/Apparel/Men's/"                                  |     |
| "Thessaloniki"          | "Home/Shop by Brand/"                                  |     |
| "Vienna"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Brisbane"              | "Home/Shop by Brand/YouTube/"                          |     |
| "Rome"                  | "Home/Shop by Brand/YouTube/"                          |     |
| "St. Louis"             | "Home/Shop by Brand/"                                  |     |
| "Salford"               | "Home/Electronics/Electronics Accessories/"            |     |
| "Oviedo"                | "Home/Apparel/"                                        |     |
| "Santa Clara"           | "Home/Shop by Brand/Google/"                           |     |
| "Chicago"               | "Nest-USA"                                             |     |
| "Antalya"               | "(not set)"                                            |     |
| "Brno"                  | "Home/Office/Notebooks & Journals/"                    |     |
| "Bucharest"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Houston"               | "Home/Shop by Brand/YouTube/"                          |     |
| "N/A"                   | "YouTube"                                              |     |
| "Portland"              | "Home/Shop by Brand/YouTube/"                          |     |
| "Ghent"                 | "Home/Accessories/"                                    |     |
| "Menlo Park"            | "Home/Shop by Brand/Google/"                           |     |
| "El Paso"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Lisbon"                | "Home/Apparel/Headgear/"                               |     |
| "Marlboro"              | "(not set)"                                            |     |
| "San Bruno"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Eau Claire"            | "Home/Shop by Brand/Google/"                           |     |
| "St. John's"            | "Home/Electronics/Power/"                              |     |
| "Waterloo"              | "Home/Apparel/"                                        |     |
| "Seattle"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Sapporo"               | "Home/Apparel/"                                        |     |
| "Columbus"              | "Home/Apparel/Men's/Men's-Outerwear/"                  |     |
| "Indianapolis"          | "Home/Office/Writing Instruments/"                     |     |
| "Helsinki"              | "(not set)"                                            |     |
| "Sao Paulo"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Hong Kong"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Westville"             | "Home/Bags/"                                           |     |
| "Marseille"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Montreuil"             | "Home/Office/"                                         |     |
| "Melbourne"             | "Home/Shop by Brand/YouTube/"                          |     |
| "South El Monte"        | "Home/Apparel/Men's/"                                  |     |
| "Piscataway Township"   | "Home/Apparel/Men's/"                                  |     |
| "Kitchener"             | "Home/Electronics/Audio/"                              |     |
| "Lahore"                | "Home/Electronics/"                                    |     |
| "Johnson City"          | "Home/Shop by Brand/Google/"                           |     |
| "Milan"                 | "Home/Shop by Brand/YouTube/"                          |     |
| "Chico"                 | "Home/Shop by Brand/YouTube/"                          |     |
| "Poznan"                | "Home/Office/Notebooks & Journals/"                    |     |
| "Amã"                   | "Home/Bags/"                                           |     |
| "Fortaleza"             | "Home/Shop by Brand/Android/"                          |     |
| "Mumbai"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Nairobi"               | "Home/Electronics/"                                    |     |
| "Raleigh"               | "Home/Apparel/Kid's/Kid's-Infant/"                     |     |
| "Alexandria"            | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Adelaide"              | "Home/Apparel/Men's/Men's-Outerwear/"                  |     |
| "Los Angeles"           | "Home/Spring Sale!/"                                   |     |
| "Ann Arbor"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Minneapolis"           | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Istanbul"              | "Home/Shop by Brand/YouTube/"                          |     |
| "Culiacan"              | "Home/Drinkware/"                                      |     |
| "Nanded"                | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Redmond"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Westlake Village"      | "(not set)"                                            |     |
| "Oxford"                | "Home/Electronics/Audio/"                              |     |
| "Redwood City"          | "Home/Nest/Nest-USA/"                                  |     |
| "Appleton"              | "Home/Electronics/"                                    |     |
| "Bratislava"            | "(not set)"                                            |     |
| "The Dalles"            | "Home/Electronics/"                                    |     |
| "Timisoara"             | "Home/Shop by Brand/Android/"                          |     |
| "Mexico City"           | "Home/Shop by Brand/YouTube/"                          |     |
| "Druid Hills"           | "Home/Office/"                                         |     |
| "Paris"                 | "Home/Shop by Brand/YouTube/"                          |     |
| "Gothenburg"            | "Home/Apparel/Women's/Women's-Performance Wear/"       |     |
| "Kovrov"                | "Home/Shop by Brand/Google/"                           |     |
| "Skopje"                | "Home/Office/"                                         |     |
| "Asuncion"              | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Phoenix"               | "Home/Office/"                                         |     |
| "Bilbao"                | "Home/Apparel/"                                        |     |
| "Boulder"               | "Home/Lifestyle/"                                      |     |
| "Ottawa"                | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Stanford"              | "Home/Apparel/Men's/"                                  |     |
| "Mountain View"         | "Waze"                                                 |     |
| "San Salvador"          | "Home/Electronics/Electronics Accessories/"            |     |
| "Detroit"               | "Home/Shop by Brand/Google/"                           |     |
| "Minato"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Manchester"            | "Home/Shop by Brand/YouTube/"                          |     |
| "Bengaluru"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Montevideo"            | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Richardson"            | "Home/Electronics/Audio/"                              |     |
| "Tampa"                 | "(not set)"                                            |     |
| "Sunnyvale"             | "Nest-USA"                                             |     |
| "Avon"                  | "Home/Apparel/Headgear/"                               |     |
| "Sacramento"            | "Home/Apparel/"                                        |     |
| "New Delhi"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Kansas City"           | "Home/Drinkware/"                                      |     |
| "Watford"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Chennai"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Santa Fe"              | "Home/Electronics/Electronics Accessories/"            |     |
| "Kirkland"              | "Home/Shop by Brand/Google/"                           |     |
| "Goose Creek"           | "Home/Apparel/Headgear/"                               |     |
| "Dubai"                 | "Home/Shop by Brand/YouTube/"                          |     |
| "Irvine"                | "Home/Shop by Brand/"                                  |     |
| "Bandung"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Akron"                 | "Home/Apparel/Men's/"                                  |     |
| "Nashville"             | "Nest-USA"                                             |     |
| "Beijing"               | "Home/Apparel/Men's/Men's-Outerwear/"                  |     |
| "Hamburg"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Milpitas"              | "Home/Shop by Brand/Google/"                           |     |
| "Prague"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Oakland"               | "Home/Shop by Brand/Google/"                           |     |
| "Shinjuku"              | "Home/Office/"                                         |     |
| "Munich"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Zurich"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Sakai"                 | "Home/Office/Notebooks & Journals/"                    |     |
| "Denver"                | "Home/Electronics/"                                    |     |
| "Yokohama"              | "Home/Shop by Brand/Google/"                           |     |
| "Nagoya"                | "Home/Shop by Brand/Google/"                           |     |
| "Charlotte"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Madrid"                | "Home/Shop by Brand/YouTube/"                          |     |
| "Ho Chi Minh City"      | "Home/Shop by Brand/YouTube/"                          |     |
| "Forest Park"           | "Home/Apparel/Men's/Men's-Outerwear/"                  |     |
| "Ahmedabad"             | "Home/Shop by Brand/YouTube/"                          |     |
| "Toronto"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Chandigarh"            | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Kharkiv"               | "Home/Office/"                                         |     |
| "Bordeaux"              | "Home/Accessories/Housewares/"                         |     |
| "Quebec City"           | "Home/Shop by Brand/YouTube/"                          |     |
| "Atlanta"               | "Home/Shop by Brand/YouTube/"                          |     |
| "Seoul"                 | "Home/Shop by Brand/YouTube/"                          |     |
| "Tempe"                 | "Home/Apparel/Men's/Men's-T-Shirts/"                   |     |
| "Lake Oswego"           | "Home/Apparel/Women's/Women's-Performance Wear/"       |     |


| City                    | Top Selling Products                                   |Volume|
|-------------------------|--------------------------------------------------------|----|
| "Mountain View"         | "Nest® Cam Indoor Security Camera - USA"               | 24 |
| "New York"              | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 14 |
| "San Francisco"         | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 12 |
| "London"                | "YouTube Twill Cap"                                    | 9  |
| "San Jose"              | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 8  |
| "Chicago"               | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 7  |
| "Los Angeles"           | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 7  |
| "Palo Alto"             | "Nest® Cam Outdoor Security Camera - USA"              | 7  |
| "Sunnyvale"             | "Nest® Cam Indoor Security Camera - USA"               | 6  |
| "Chennai"               | "YouTube RFID Journal"                                 | 5  |
| "Hyderabad"             | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 5  |
| "Seattle"               | "Google Laptop and Cell Phone Stickers"                | 4  |
| "Toronto"               | "YouTube Trucker Hat"                                  | 4  |
| "Atlanta"               | "Google Men's 100% Cotton Short Sleeve Hero Tee Navy"  | 4  |
| "Chennai"               | "YouTube Twill Cap"                                    | 4  |
| "Mumbai"                | "YouTube Men's Vintage Tee"                            | 3  |
| "Berlin"                | "YouTube Wool Heather Cap Heather/Black"               | 3  |
| "Seattle"               | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 3  |
| "Paris"                 | "Google Men's Performance Polo Grey/Black"             | 3  |
| "Austin"                | "Google Women's Short Sleeve Shirt Blue"               | 3  |
| "Houston"               | "Google Men's Long Sleeve Raglan Ocean Blue"           | 3  |
| "Melbourne"             | "YouTube Notebook and Pen Set"                         | 3  |
| "Sydney"                | "YouTube Trucker Hat"                                  | 3  |
| "Houston"               | "YouTube Men's Short Sleeve Hero Tee Black"            | 3  |
| "Dublin"                | "You Tube Toddler Short Sleeve Tee Red"                | 3  |
| "Cambridge"             | "Galaxy Screen Cleaning Cloth"                         | 3  |
| "Sydney"                | "Basecamp Explorer Powerbank Flashlight"               | 3  |
| "Ann Arbor"             | "Google Men's Vintage Badge Tee Black"                 | 2  |
| "New Delhi"             | "YouTube Custom Decals"                                | 2  |
| "Gurgaon"               | "Android Men's Vintage Tank"                           | 2  |
| "Mexico City"           | "Women's YouTube Short Sleeve Hero Tee Black"          | 2  |
| "Munich"                | "YouTube Twill Cap"                                    | 2  |
| "Bengaluru"             | "YouTube Onesie Heather"                               | 2  |
| "Washington"            | "YouTube Men's 3/4 Sleeve Henley"                      | 2  |
| "Jakarta"               | "Google Women's 1/4 Zip Jacket Charcoal"               | 2  |
| "Bangkok"               | "YouTube Men's Vintage Henley"                         | 2  |
| "Eau Claire"            | "YouTube Men's Short Sleeve Hero Tee Charcoal"         | 2  |
| "Pittsburgh"            | "Collapsible Shopping Bag"                             | 2  |
| "Tel Aviv-Yafo"         | "YouTube Hard Cover Journal"                           | 2  |
| "Warsaw"                | "Google Laptop and Cell Phone Stickers"                | 2  |
| "Cupertino"             | "YouTube Men's Vintage Tank"                           | 2  |
| "Santa Clara"           | "Google Men's Quilted Insulated Vest Black"            | 2  |
| "Manila"                | "YouTube Men's Short Sleeve Hero Tee White"            | 2  |
| "Minato"                | "Google Men's 100% Cotton Short Sleeve Hero Tee White" | 2  |
| "Zurich"                | "Google Men's Vintage Badge Tee Black"                 | 2  |
| "Istanbul"              | "Google G Noise-reducing Bluetooth Headphones"         | 2  |
| "Boston"                | "Collapsible Shopping Bag"                             | 2  |
| "Redmond"               | "YouTube RFID Journal"                                 | 2  |
| "Kirkland"              | "Google Women's Lightweight Microfleece Jacket"        | 2  |
| "Moscow"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Neipu Township"        | "Home/Apparel/Women's/Women's-Outerwear/"              |    |
| "Calgary"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Wrexham"               | "Home/Shop by Brand/"                                  |    |
| "Cluj-Napoca"           | "Home/Apparel/"                                        |    |
| "San Antonio"           | "Home/Shop by Brand/YouTube/"                          |    |
| "Nice"                  | "Home/Drinkware/"                                      |    |
| "Coventry"              | "Home/Shop by Brand/YouTube/"                          |    |
| "Cape Town"             | "Home/Apparel/Men's/"                                  |    |
| "Courbevoie"            | "Home/Shop by Brand/"                                  |    |
| "Egham"                 | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Zhongli District"      | "Home/Shop by Brand/YouTube/"                          |    |
| "Vancouver"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Esbjerg"               | "Home/Apparel/Women's/Women's-T-Shirts/"               |    |
| "Santiago"              | "Home/Office/"                                         |    |
| "Jersey City"           | "Home/Bags/Backpacks/"                                 |    |
| "Berkeley"              | "Home/Apparel/Kid's/Kid's-Infant/"                     |    |
| "Copenhagen"            | "Home/Apparel/Headgear/"                               |    |
| "Oslo"                  | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Frankfurt"             | "Home/Shop by Brand/Google/"                           |    |
| "San Jose"              | "Home/Spring Sale!/"                                   |    |
| "Cambridge"             | "Home/Shop by Brand/Google/"                           |    |
| "Rio de Janeiro"        | "Home/Shop by Brand/Google/"                           |    |
| "Salem"                 | "Home/Shop by Brand/YouTube/"                          |    |
| "Tel Aviv-Yafo"         | "Home/Shop by Brand/YouTube/"                          |    |
| "Perth"                 | "Home/Shop by Brand/YouTube/"                          |    |
| "Hayward"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Jaipur"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Charlottetown"         | "Home/Office/"                                         |    |
| "Cork"                  | "Home/Accessories/Stickers/"                           |    |
| "Columbia"              | "Home/Electronics/"                                    |    |
| "New York"              | "Lifestyle/"                                           |    |
| "Greer"                 | "Home/Apparel/Men's/Men's-Outerwear/"                  |    |
| "San Francisco"         | "Nest-USA"                                             |    |
| "Makati"                | "Home/Electronics/Audio/"                              |    |
| "Berlin"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Dallas"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Jacksonville"          | "Home/Electronics/Electronics Accessories/"            |    |
| "Chuo"                  | "Home/Apparel/Women's/"                                |    |
| "Krakow"                | "Home/Drinkware/"                                      |    |
| "Barcelona"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Warsaw"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Edmonton"              | "Home/Shop by Brand/YouTube/"                          |    |
| "Rosario"               | "Home/Apparel/Men's/"                                  |    |
| "Shibuya"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Pittsburgh"            | "Home/Office/Notebooks & Journals/"                    |    |
| "Jakarta"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Boston"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Burnaby"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Rexburg"               | "Home/Drinkware/"                                      |    |
| "Ashburn"               | "Home/Lifestyle/Fun/"                                  |    |
| "Ipoh"                  | "Home/Accessories/Housewares/"                         |    |
| "Patna"                 | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "London"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Doha"                  | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Rotterdam"             | "Home/Apparel/Headgear/"                               |    |
| "Bellflower"            | "Home/Shop by Brand/YouTube/"                          |    |
| "Philadelphia"          | "Home/Shop by Brand/YouTube/"                          |    |
| "Hyderabad"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Athens"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Parsippany-Troy Hills" | "Home/Apparel/Men's/Men's-Outerwear/"                  |    |
| "Pozuelo de Alarcon"    | "Home/Shop by Brand/YouTube/"                          |    |
| "Medellin"              | "Home/Drinkware/"                                      |    |
| "Glasgow"               | "Home/Electronics/Audio/"                              |    |
| "Monterrey"             | "Home/Office/"                                         |    |
| "San Diego"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Madison"               | "Home/Bags/"                                           |    |
| "Council Bluffs"        | "Home/Apparel/"                                        |    |
| "Amsterdam"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Osaka"                 | "Home/Shop by Brand/Google/"                           |    |
| "Lucknow"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Karachi"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Kolkata"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Bogota"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Wellesley"             | "Home/Office/Writing Instruments/"                     |    |
| "Dublin"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Palo Alto"             | "Nest-USA"                                             |    |
| "Iasi"                  | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "La Victoria"           | "Home/Shop by Brand/YouTube/"                          |    |
| "San Mateo"             | "Home/Clearance Sale/"                                 |    |
| "Buenos Aires"          | "Home/Shop by Brand/YouTube/"                          |    |
| "Sandton"               | "Home/Electronics/"                                    |    |
| "Las Vegas"             | "Home/Apparel/Men's/Men's-Outerwear/"                  |    |
| "Belo Horizonte"        | "Home/Bags/Shopping and Totes/"                        |    |
| "Odessa"                | "Home/Accessories/Drinkware/"                          |    |
| "Pleasanton"            | "Home/Bags/"                                           |    |
| "Saint Petersburg"      | "Home/Shop by Brand/YouTube/"                          |    |
| "Sydney"                | "Nest-USA"                                             |    |
| "Kalamazoo"             | "(not set)"                                            |    |
| "Vilnius"               | "Home/Apparel/Men's/"                                  |    |
| "Thessaloniki"          | "Home/Shop by Brand/"                                  |    |
| "Vienna"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Brisbane"              | "Home/Shop by Brand/YouTube/"                          |    |
| "Rome"                  | "Home/Shop by Brand/YouTube/"                          |    |
| "St. Louis"             | "Home/Shop by Brand/"                                  |    |
| "Salford"               | "Home/Electronics/Electronics Accessories/"            |    |
| "Oviedo"                | "Home/Apparel/"                                        |    |
| "Santa Clara"           | "Home/Shop by Brand/Google/"                           |    |
| "Chicago"               | "Nest-USA"                                             |    |
| "Antalya"               | "(not set)"                                            |    |
| "Brno"                  | "Home/Office/Notebooks & Journals/"                    |    |
| "Bucharest"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Houston"               | "Home/Shop by Brand/YouTube/"                          |    |
| "N/A"                   | "YouTube"                                              |    |
| "Portland"              | "Home/Shop by Brand/YouTube/"                          |    |
| "Ghent"                 | "Home/Accessories/"                                    |    |
| "Menlo Park"            | "Home/Shop by Brand/Google/"                           |    |
| "El Paso"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Lisbon"                | "Home/Apparel/Headgear/"                               |    |
| "Marlboro"              | "(not set)"                                            |    |
| "San Bruno"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Eau Claire"            | "Home/Shop by Brand/Google/"                           |    |
| "St. John's"            | "Home/Electronics/Power/"                              |    |
| "Waterloo"              | "Home/Apparel/"                                        |    |
| "Seattle"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Sapporo"               | "Home/Apparel/"                                        |    |
| "Columbus"              | "Home/Apparel/Men's/Men's-Outerwear/"                  |    |
| "Indianapolis"          | "Home/Office/Writing Instruments/"                     |    |
| "Helsinki"              | "(not set)"                                            |    |
| "Sao Paulo"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Hong Kong"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Westville"             | "Home/Bags/"                                           |    |
| "Marseille"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Montreuil"             | "Home/Office/"                                         |    |
| "Melbourne"             | "Home/Shop by Brand/YouTube/"                          |    |
| "South El Monte"        | "Home/Apparel/Men's/"                                  |    |
| "Piscataway Township"   | "Home/Apparel/Men's/"                                  |    |
| "Kitchener"             | "Home/Electronics/Audio/"                              |    |
| "Lahore"                | "Home/Electronics/"                                    |    |
| "Johnson City"          | "Home/Shop by Brand/Google/"                           |    |
| "Milan"                 | "Home/Shop by Brand/YouTube/"                          |    |
| "Chico"                 | "Home/Shop by Brand/YouTube/"                          |    |
| "Poznan"                | "Home/Office/Notebooks & Journals/"                    |    |
| "Amã"                   | "Home/Bags/"                                           |    |
| "Fortaleza"             | "Home/Shop by Brand/Android/"                          |    |
| "Mumbai"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Nairobi"               | "Home/Electronics/"                                    |    |
| "Raleigh"               | "Home/Apparel/Kid's/Kid's-Infant/"                     |    |
| "Alexandria"            | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Adelaide"              | "Home/Apparel/Men's/Men's-Outerwear/"                  |    |
| "Los Angeles"           | "Home/Spring Sale!/"                                   |    |
| "Ann Arbor"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Minneapolis"           | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Istanbul"              | "Home/Shop by Brand/YouTube/"                          |    |
| "Culiacan"              | "Home/Drinkware/"                                      |    |
| "Nanded"                | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Redmond"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Westlake Village"      | "(not set)"                                            |    |
| "Oxford"                | "Home/Electronics/Audio/"                              |    |
| "Redwood City"          | "Home/Nest/Nest-USA/"                                  |    |
| "Appleton"              | "Home/Electronics/"                                    |    |
| "Bratislava"            | "(not set)"                                            |    |
| "The Dalles"            | "Home/Electronics/"                                    |    |
| "Timisoara"             | "Home/Shop by Brand/Android/"                          |    |
| "Mexico City"           | "Home/Shop by Brand/YouTube/"                          |    |
| "Druid Hills"           | "Home/Office/"                                         |    |
| "Paris"                 | "Home/Shop by Brand/YouTube/"                          |    |
| "Gothenburg"            | "Home/Apparel/Women's/Women's-Performance Wear/"       |    |
| "Kovrov"                | "Home/Shop by Brand/Google/"                           |    |
| "Skopje"                | "Home/Office/"                                         |    |
| "Asuncion"              | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Phoenix"               | "Home/Office/"                                         |    |
| "Bilbao"                | "Home/Apparel/"                                        |    |
| "Boulder"               | "Home/Lifestyle/"                                      |    |
| "Ottawa"                | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Stanford"              | "Home/Apparel/Men's/"                                  |    |
| "Mountain View"         | "Waze"                                                 |    |
| "San Salvador"          | "Home/Electronics/Electronics Accessories/"            |    |
| "Detroit"               | "Home/Shop by Brand/Google/"                           |    |
| "Minato"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Manchester"            | "Home/Shop by Brand/YouTube/"                          |    |
| "Bengaluru"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Montevideo"            | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Richardson"            | "Home/Electronics/Audio/"                              |    |
| "Tampa"                 | "(not set)"                                            |    |
| "Sunnyvale"             | "Nest-USA"                                             |    |
| "Avon"                  | "Home/Apparel/Headgear/"                               |    |
| "Sacramento"            | "Home/Apparel/"                                        |    |
| "New Delhi"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Kansas City"           | "Home/Drinkware/"                                      |    |
| "Watford"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Chennai"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Santa Fe"              | "Home/Electronics/Electronics Accessories/"            |    |
| "Kirkland"              | "Home/Shop by Brand/Google/"                           |    |
| "Goose Creek"           | "Home/Apparel/Headgear/"                               |    |
| "Dubai"                 | "Home/Shop by Brand/YouTube/"                          |    |
| "Irvine"                | "Home/Shop by Brand/"                                  |    |
| "Bandung"               | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Akron"                 | "Home/Apparel/Men's/"                                  |    |
| "Nashville"             | "Nest-USA"                                             |    |
| "Beijing"               | "Home/Apparel/Men's/Men's-Outerwear/"                  |    |
| "Hamburg"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Milpitas"              | "Home/Shop by Brand/Google/"                           |    |
| "Prague"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Oakland"               | "Home/Shop by Brand/Google/"                           |    |
| "Shinjuku"              | "Home/Office/"                                         |    |
| "Munich"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Zurich"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Sakai"                 | "Home/Office/Notebooks & Journals/"                    |    |
| "Denver"                | "Home/Electronics/"                                    |    |
| "Yokohama"              | "Home/Shop by Brand/Google/"                           |    |
| "Nagoya"                | "Home/Shop by Brand/Google/"                           |    |
| "Charlotte"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Madrid"                | "Home/Shop by Brand/YouTube/"                          |    |
| "Ho Chi Minh City"      | "Home/Shop by Brand/YouTube/"                          |    |
| "Forest Park"           | "Home/Apparel/Men's/Men's-Outerwear/"                  |    |
| "Ahmedabad"             | "Home/Shop by Brand/YouTube/"                          |    |
| "Toronto"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Chandigarh"            | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Kharkiv"               | "Home/Office/"                                         |    |
| "Bordeaux"              | "Home/Accessories/Housewares/"                         |    |
| "Quebec City"           | "Home/Shop by Brand/YouTube/"                          |    |
| "Atlanta"               | "Home/Shop by Brand/YouTube/"                          |    |
| "Seoul"                 | "Home/Shop by Brand/YouTube/"                          |    |
| "Tempe"                 | "Home/Apparel/Men's/Men's-T-Shirts/"                   |    |
| "Lake Oswego"           | "Home/Apparel/Women's/Women's-Performance Wear/"       |    |


**Question 5: Can we summarize the impact of revenue generated from each city/country?**

### SQL Queries:

  SELECT all_sessions.country, 
  SUM(analytics.units_sold * analytics.unit_price) AS revenue
  FROM all_sessions
  INNER JOIN analytics ON all_sessions.visit_id = analytics.visit_id
  GROUP BY all_sessions.country
  ORDER BY revenue DESC
  LIMIT 30;

  SELECT all_sessions.city, 
  SUM(analytics.units_sold * analytics.unit_price) AS revenue
  FROM all_sessions
  INNER JOIN analytics ON all_sessions.visit_id = analytics.visit_id
  GROUP BY all_sessions.city
  ORDER BY revenue DESC
  LIMIT 34;


### Answer:

| Countries               | Revenue
|-------------------------|--------------------------------------------------------|
| "United States"         | 41139                                                  |
| "Sweden"                | 654                                                    |
| "Mexico"                | 494                                                    |
| "Canada"                | 412                                                    |
| "Ireland"               | 308                                                    |
| "United Kingdom"        | 279                                                    |
| "Japan"                 | 218                                                    |
| "Chile"                 | 198                                                    |
| "Maldives"              | 198                                                    |
| "Hong Kong"             | 196                                                    |
| "Indonesia"             | 99                                                     |
| "Netherlands"           | 99                                                     |
| "Israel"                | 90                                                     |
| "Switzerland"           | 80                                                     |
| "Thailand"              | 78                                                     |
| "Egypt"                 | 76                                                     |
| "Belgium"               | 48                                                     |
| "India"                 | 35                                                     |
| "France"                | 34                                                     |
| "Vietnam"               | 32                                                     |
| "Colombia"              | 32                                                     |
| "Taiwan"                | 28                                                     |
| "Bulgaria"              | 24                                                     |
| "Denmark"               | 24                                                     |
| "Germany"               | 22                                                     |
| "Austria"               | 12                                                     |
| "Singapore"             | 7                                                      |
| "Romania"               | 4                                                      |
| "Australia"             | 3                                                      |
| "South Korea"           | 2                                                      |
| "South Korea"           | 2                                                      |



| City            |Revenue|
|-----------------|-------|
| "New York"      | 11240 |
| "Sunnyvale"     | 6700  |
| "Mountain View" | 4584  |
| "Chicago"       | 2869  |
| "Seattle"       | 1959  |
| "San Francisco" | 1650  |
| "Palo Alto"     | 1106  |
| "San Jose"      | 765   |
| "Pittsburgh"    | 528   |
| "Dublin"        | 308   |
| "London"        | 279   |
| "San Bruno"     | 217   |
| "Santiago"      | 198   |
| "Toronto"       | 101   |
| "Tel Aviv-Yafo" | 90    |
| "Atlanta"       | 88    |
| "Bangkok"       | 72    |
| "Zurich"        | 64    |
| "Ann Arbor"     | 52    |
| "Washington"    | 37    |
| "Bogota"        | 32    |
| "Kirkland"      | 29    |
| "Austin"        | 27    |
| "Dallas"        | 18    |
| "Hong Kong"     | 18    |
| "Paris"         | 17    |
| "Houston"       | 15    |
| "Berlin"        | 12    |
| "Munich"        | 10    |
| "Singapore"     | 7     |
| "Detroit"       | 6     |
| "Hyderabad"     | 5     |
| "Cupertino"     | 0     |




