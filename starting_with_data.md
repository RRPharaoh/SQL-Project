### Question 1: 
List all of the items that went unordered by name.

#### SQL Queries:

```
  SELECT sku, name
  FROM products
  WHERE ordered_quantity = 0
```

Answer: 

| Product Sku       | Name                                                  |
|-------------------|-------------------------------------------------------|
| "GGADFBSBKS42347" | "PC gaming speakers"                                  |
| "GGOEGAAX0581"    | " Women's Colorblock Tee White"                       |
| "9180850"         | "Ballpoint Stylus Pen"                                |
| "9183118"         | " Women's Fleece Hoodie Black"                        |
| "9183203"         | " Device Holder Sticky Pad"                           |
| "9184697"         | " Mood Original Window Decal"                         |
| "9183225"         | " Luggage Tag"                                        |
| "9182723"         | " Men's 100% Cotton Short Sleeve Hero Tee White"      |
| "9182720"         | " Men's Short Sleeve Badge Tee Charcoal"              |
| "9182772"         | " Women's Performance Full Zip Jacket Black"          |
| "9182755"         | " Men's Colorblock Tee White/Heather"                 |
| "9184720"         | " Women's Short Sleeve Hero Tee Sky Blue"             |
| "9182761"         | " Women's Yoga Jacket Black"                          |
| "9184689"         | " Men's Short Sleeve Tee"                             |
| "9184682"         | " Mobile Phone Vent Mount"                            |
| "9183234"         | " Learning Thermostat 3rd Gen-USA - Stainless Steel"  |
| "9182859"         | " Toddler Raglan Shirt Blue Heather/Navy"             |
| "9182863"         | " Toddler Sports T-shirt Red"                         |
| "9180811"         | "Plastic Sliding Flashlight"                          |
| "9182750"         | " Men's Performance 1/4 Zip Pullover Heather/Black"   |
| "9183205"         | " Zipper-front Sports Bag"                            |
| "9182980"         | " Pet Feeding Mat"                                    |
| "9180813"         | " Tube Power Bank"                                    |
| "9182778"         | " Women's Softshell Jacket Black/Grey"                |
| "9184683"         | " Women's Short Sleeve Tee"                           |
| "9182774"         | " Women's Yoga Pants"                                 |
| "9183220"         | " Leather Journal-Brown"                              |
| "9182780"         | " Women's Shell Jacket Blue/Black"                    |
| "9182179"         | "Android Women's Short Sleeve Badge Tee Dark Heather" |
| "9182997"         | " 17oz Stainless Steel Sport Bottle"                  |
| "9180770"         | "Yoga Mat Blue"                                       |
| "9184681"         | " 17 oz Double Wall Stainless Steel Insulated Bottle" |
| "9183086"         | " Youth Girl Tee Green"                               |
| "9181573"         | " Snapback Hat Black"                                 |
| "9180757"         | "Yoga Block"                                          |
| "9182812"         | " Infant Zip Hood Pink"                               |
| "9181019"         | " Tri-blend Hoodie Grey"                              |
| "GGOEGAAX0314"    | " Men's 3/4 Sleeve Henley"                            |
| "9180764"         | " Canvas Tote Natural/Navy"                           |
| "9182739"         | " Men's Watershed Full Zip Hoodie Grey"               |
| "9182793"         | " Men's Long & Lean Tee Charcoal"                     |
| "9183214"         | " Hard Cover Journal"                                 |
| "9180844"         | "Gunmetal Roller Ball Pen"                            |
| "9182764"         | " Women's Convertible Vest-Jacket Black"              |
| "9182828"         | " Toddler Short Sleeve T-shirt Royal Blue"            |
| "9182751"         | " Men's Performance Full Zip Jacket Black"            |
| "9184695"         | " Baby on Board Window Decal"                         |
| "GGOEYHPA003610"  | " Wool Heather Cap Heather/Black"                     |
| "9182581"         | " Women's Fleece Hoodie"                              |
| "9182771"         | " Women's 1/4 Zip Jacket Charcoal"                    |
| "9182743"         | " Men's Microfiber 1/4 Zip Pullover Blue/Indigo"      |
| "9180838"         | "Metal Texture Roller Pen"                            |
| "9182569"         | " Men's                                               |
| "9182737"         | " Women's 3/4 Sleeve Baseball Raglan Heather/Black"   |
| "GGOEYHPA003510"  | " Trucker Hat"                                        |
| "9184721"         | "BLM Sweatshirt"                                      |
| "9182898"         | "Android Youth Short Sleeve T-shirt Aqua"             |
| "9183112"         | " Men's Fleece Hoodie Black"                          |
| "9184734"         | " Learning Thermostat 3rd Gen-USA - Copper"           |
| "9181572"         | "Android Wool Heather Cap Heather/Black"              |
| "9182705"         | "Android Men's Long & Lean Badge Tee Charcoal"        |
| "9182785"         | " Women's Lightweight Microfleece Jacket"             |
| "9180767"         | " Slim Utility Travel Bag"                            |
| "9182502"         | " Women's Yoga Jacket Black"                          |
| "9183186"         | " G Noise-reducing Bluetooth Headphones"              |
| "9180905"         | " Men's Long Sleeve Raglan Ocean Blue"                |
| "9183152"         | " Youth Short Sleeve Tee Red"                         |
| "9182777"         | " Women's Performance Golf Polo Blue"                 |
| "9182658"         | " Women's Short Sleeve Hero Tee Sky Blue"             |
| "9182742"         | " Men's Convertible Vest-Jacket Pewter"               |
| "9181151"         | "Gift Card - $50.00"                                  |
| "9180782"         | "Seat Pack Organizer"                                 |
| "9183226"         | "Android Luggage Tag"                                 |
| "9183228"         | " Cam Indoor Security Camera - USA"                   |
| "9182999"         | " Bongo Cupholder Bluetooth Speaker"                  |
| "9182909"         | " Collapsible Pet Bowl"                               |
| "9182559"         | "Android Men's Vintage Henley"                        |
| "9181150"         | "Gift Card - $250.00"                                 |
| "9184705"         | " Women's Typography Short Sleeve Tee"                |
| "9180840"         | "Satin Black Ballpoint Pen"                           |
| "GGOEGHPJ080010"  | " French Terry Cap"                                   |
| "9182995"         | " Car Clip Phone Holder"                              |
| "9182752"         | " Men's Short Sleeve Performance Badge Tee Charcoal"  |
| "GGOEGAAX0349"    | "Android BTTF Moonshot Graphic Tee"                   |
| "GGOEGAAX0577"    | " Women's Performance Golf Polo Blue"                 |
| "9182383"         | " Men's Watershed Full Zip Hoodie Grey"               |
| "9182587"         | "Android Women's Fleece Hoodie"                       |
| "9183000"         | " Pocket Bluetooth Speaker"                           |
| "GGOEGAAX0346"    | " Men's Vintage Tee"                                  |
| "9183194"         | " Executive Umbrella"                                 |
| "9180868"         | "Crunch Noise Dog Toy"                                |
| "GGOEWXXX0827"    | " Women's Short Sleeve Tee"                           |
| "GGOEGAAX0598"    | " Men's Convertible Vest-Jacket Pewter"               |
| "9180808"         | "Basecamp Explorer Powerbank Flashlight"              |
| "9184676"         | "UpCycled Handlebar Bag"                              |
| "9181149"         | "Gift Card - $25.00"                                  |
| "9182706"         | "Android Stretch Fit Hat"                             |
| "9180862"         | " Screen Cleaning Cloth"                              |
| "9183106"         | " Women's Performance Hero Tee Gunmetal"              |
| "GGOEGAAX0335"    | " Men's Long Sleeve Pullover Badge Tee Heather"       |
| "9182701"         | "Android Men's Long Sleeve Badge Crew Tee Heather"    |
| "9183210"         | " RFID Journal"                                       |
| "GGOEGAAX0576"    | " Women's Softshell Jacket Black/Grey"                |
| "9180792"         | "20 oz Stainless Steel Insulated Tumbler"             |
| "9182753"         | " Men's Weatherblock Shell Jacket Black"              |
| "9183221"         | " Leather Journal-Black"                              |
| "GGOEYOBR078599"  | " Luggage Tag"                                        |
| "GGOEGHPA003010"  | " Wool Heather Cap Heather/Navy"                      |
| "9182176"         | "Android Women's Short Sleeve Badge Tee Dark Heather" |
| "9182765"         | " Women's Convertible Vest-Jacket Sea Foam Green"     |
| "9180771"         | "Yoga Mat Purple"                                     |
| "9182820"         | " Baby Essentials Set"                                |
| "9183223"         | " Spiral Leather Journal"                             |
| "9182726"         | " Men's Long & Lean Tee Charcoal"                     |
| "9183015"         | " Onesie Heather"                                     |
| "GGOEWXXX0834"    | " Women's Typography Short Sleeve Tee"                |
| "GGOEGAAX0729"    | " Women's Performance Hero Tee Gunmetal"              |
| "9180833"         | "Rubber Grip Ballpoint Pen 4 Pack"                    |
| "9182709"         | "Android Women's Long Sleeve Blended Cardigan Grey"   |
| "9180781"         | "Suitcase Organizer Cubes"                            |
| "9182769"         | " Women's Short Sleeve Performance Tee Pewter"        |
| "9181148"         | "Gift Card- $100.00"                                  |
| "9182173"         | " Stylus Pen w/ LED Light"                            |
| "9180748"         | "Android Lunch Kit"                                   |
| "9182754"         | " Men's Softshell Jacket Black/Grey"                  |
| "9181137"         | " Alpine Style Backpack"                              |
| "9184737"         | " Pack of 9 Decal Set"                                |
| "9182746"         | " Men's Quilted Insulated Vest Battleship Grey"       |
| "GGOEGDHB072099"  | " Insulated Stainless Steel Bottle"                   |
| "9180806"         | "Clip-on Compact Charger"                             |
| "9180824"         | "Foam Can and Bottle Cooler"                          |
| "9182773"         | " Women's Short Sleeve Performance Tee Charcoal"      |
| "9183091"         | " Youth Baseball Raglan Heather/Black"                |
| "9182903"         | "Android Youth Short Sleeve T-shirt Pewter"           |
| "9180814"         | "Micro Wireless Earbud"                               |
| "9180759"         | " Lunch Bag"                                          |
| "9182722"         | " Men's 100% Cotton Short Sleeve Hero Tee Navy"       |
| "9184620"         | " Men's Performance Full Zip Jacket Black"            |
| "9180754"         | "8 pc Android Sticker Sheet"                          |
| "9182605"         | " Women's Tee Grey"                                   |
| "9184698"         | " Mood Ninja Window Decal"                            |
| "9180809"         | " Flashlight"                                         |
| "9183213"         | "Android Hard Cover Journal"                          |
| "9181139"         | "Waterproof Backpack"                                 |
| "9182788"         | "Yoga Mat"                                            |
| "9183240"         | "25L Classic Rucksack"                                |
| "9182873"         | "Android Toddler Short Sleeve T-shirt Pink"           |
| "9182721"         | " Men's 100% Cotton Short Sleeve Hero Tee Black"      |
| "9180756"         | "Windup Android"                                      |
| "9183230"         | " Protect Smoke + CO White Battery Alarm-USA"         |
| "9182738"         | " Women's Long Sleeve Blended Cardigan Charcoal"      |
| "9182593"         | " Men's Pullover Hoodie Grey"                         |
| "9182781"         | " Women's Short Sleeve Hero Tee Black"                |
| "9182575"         | "Android Men's                                        |
| "9182784"         | " Women's Short Sleeve Hero Tee White"                |
| "9181664"         | "Waterproof Gear Bag"                                 |
| "9182725"         | " Men's Long & Lean Tee Grey"                         |
| "GGOEGHPA002910"  | " Trucker Hat"                                        |
| "9180820"         | " Doodle Decal"                                       |
| "9180793"         | "26 oz Double Wall Insulated Bottle"                  |
| "9180766"         | "Sport Bag"                                           |
| "9184675"         | "UpCycled Bike Saddle Bag"                            |
| "9184708"         | " Women's Typography Short Sleeve Tee"                |
| "9183096"         | " Youth Sports Tee Navy"                              |
| "9180779"         | "1 oz Hand Sanitizer"                                 |
| "GGOEYDHJ019399"  | "24 oz                                                |
| "9182848"         | " Toddler Hoodie Royal Blue"                          |
| "9181138"         | " Rucksack"                                           |
| "9182740"         | " Men's Airflow 1/4 Zip Pullover Black"               |
| "9184733"         | " Learning Thermostat 3rd Gen-USA - White"            |
| "9182719"         | " Men's Short Sleeve Hero Tee Charcoal"               |
| "9182553"         | " Men's Vintage Henley"                               |
| "9182714"         | " Men's Long Sleeve Raglan Ocean Blue"                |
| "GGOEAXXX0833"    | "Android Men's Paradise Short Sleeve Tee Olive"       |
| "9182816"         | " Infant Zip Hood Royal Blue"                         |
| "9180762"         | " Tote Bag"                                           |
| "9183222"         | " Leather Perforated Journal"                         |
| "9180769"         | " Laptop Backpack"                                    |
| "9183196"         | " 4400mAh Power Bank"                                 |
| "9183212"         | "Android RFID Journal"                                |
| "9183219"         | " Leather Journal"                                    |
| "9184707"         | " Women's Typography Short Sleeve Tee"                |
| "9183188"         | " High Capacity 10,400mAh Charger"                    |
| "9182599"         | " Women's Long Sleeve Tee Lavender"                   |
| "9182717"         | " Men's Short Sleeve Hero Tee Light Blue"             |
| "9183229"         | " Cam Outdoor Security Camera - USA"                  |
| "9183239"         | "25L Classic Rucksack"                                |
| "9182741"         | " Men's Airflow 1/4 Zip Pullover Lapis"               |
| "9182745"         | " Men's Quilted Insulated Vest Black"                 |
| "9183241"         | "25L Classic Rucksack"                                |
| "9182806"         | " Onesie Green"                                       |


### Question 2: 
what portion of channel impressions were organic?

#### SQL Queries:

```
  SELECT *
  FROM all_sessions
  WHERE channel_impressions = 'Organic Search';
  ```

#### Answer:
8.6%
Total rows: 1000 of 8653


### Question 3: 

What are the top 10 most expensive items being sold?

#### SQL Queries:

```
  SELECT all_sessions.v2_product_name, analytics.unit_price
  From all_sessions
  INNER JOIN analytics on all_sessions.visit_id = analytics.visit_id
  ORDER BY unit_price desc
  LIMIT 10;
```


Answer:

| Product                                         | Cost                                                  |
|-------------------------------------------------|-------------------------------------------------------|
| "Nest® Learning Thermostat 3rd Gen-USA - White" | 395                                                   |
| "Nest® Learning Thermostat 3rd Gen-USA - White" | 395                                                   |
| "Nest® Learning Thermostat 3rd Gen-USA - White" | 395                                                   |
| "Nest® Learning Thermostat 3rd Gen-USA - White" | 395                                                   |
| "SPF-15 Slim & Slender Lip Balm"                | 316                                                   |
| "SPF-15 Slim & Slender Lip Balm"                | 316                                                   |
| "SPF-15 Slim & Slender Lip Balm"                | 316                                                   |
| "SPF-15 Slim & Slender Lip Balm"                | 316                                                   |
| "SPF-15 Slim & Slender Lip Balm"                | 316                                                   |
| "SPF-15 Slim & Slender Lip Balm"                | 316                                                   |
