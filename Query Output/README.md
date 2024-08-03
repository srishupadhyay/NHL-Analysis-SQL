## Tables Output
| Table_Name              | Number_of_Attributes | Row_Count |
|-------------------------|----------------------|-----------|
| canada_births_1991_2022$ | 3                    | 384       |
| nhl_rosters$            | 19                   | 54883     |
| nhl_teams$              | 2                    | 59        |

### Q1. Write a query to calculate the total number of NHL player births for each year from 1991 to 2000.<br/>

| Birth_year | Player_count |
|------------|---------------|
| 1991       | 965           |
| 1992       | 1062          |
| 1993       | 877           |
| 1994       | 948           |
| 1995       | 744           |
| 1996       | 724           |
| 1997       | 590           |
| 1998       | 510           |
| 1999       | 369           |
| 2000       | 216           |

### Q2. Write a SQL query to calculate the top 3 teams with highest number of players who play forward.<br/>

| Player_count | Team_code |
|--------------|-----------|
| 1117         | NYR       |
| 1063         | BOS       |
| 1020         | CHI       |

### Q3. Write a SQL query to find players whose birth city starts with 'New '. Classify these players into 'Young' and 'Experienced' based on whether their birth year is after 1995.<br/>


| Player_Id | Player_Name      | Birth_City        | Date       | Player_Classification |
|-----------|------------------|-------------------|------------|-----------------------|
| 8445042   | Frank Beisler    | New Haven         | 1913-10-18 | Experienced           |
| 8445075   | Pete Bessone     | New Bedford       | 1913-01-13 | Experienced           |
| 8445451   | Doug Berry       | New Westminster   | 1957-06-03 | Experienced           |
| 8445542   | Hal Cooper       | New Liskeard      | 1915-08-29 | Experienced           |
| 8445995   | Jack Dyte        | New Liskeard      | 1918-10-13 | Experienced           |
| 8446186   | Trevor Fahey     | New Waterford     | 1944-01-04 | Experienced           |
| 8446368   | Matt Delguidice  | New Haven         | 1967-03-05 | Experienced           |
| 8446674   | Herb Hamel       | New Hamburg       | 1904-06-08 | Experienced           |
| 8447029   | Troy Gamble      | New Glasgow       | 1967-04-07 | Experienced           |
| 8447130   | Walter Kalbfleish| New Hamburg       | 1911-12-18 | Experienced           |
| 8447536   | Lowell MacDonald | New Glasgow       | 1941-08-30 | Experienced           |
| 8447899   | Gus Mortson      | New Liskeard      | 1925-01-24 | Experienced           |
| 8448053   | Brent Hughes     | New Westminster   | 1966-04-05 | Experienced           |
| 8448094   | Glenn Patrick    | New York City     | 1950-04-26 | Experienced           |
| 8448190   | Tracy Pratt      | New York City     | 1943-03-08 | Experienced           |
| 8448303   | Jim Johnson      | New Hope          | 1962-09-08 | Experienced           |
| 8448689   | Brian Lawton     | New Brunswick     | 1965-06-29 | Experienced           |
| 8448783   | Ed Sandford      | New Toronto       | 1928-08-20 | Experienced           |
| 8448873   | Mark Lofthouse   | New Westminster   | 1957-04-21 | Experienced           |
| 8448939   | David Mackey     | New Westminster   | 1966-07-24 | Experienced           |
| 8449399   | William Mcdougall| New Waterford     | 1966-08-10 | Experienced           |
| 8449468   | Barry Wilcox     | New Westminster   | 1948-04-23 | Experienced           |
| 8449497   | Thomas Mcmurchy  | New Westminster   | 1963-12-02 | Experienced           |
| 8449742   | Brian Mullen     | New York City     | 1962-03-16 | Experienced           |
| 8449743   | Joe Mullen       | New York City     | 1957-02-26 | Experienced           |
| 8449828   | Richard Bittner  | New Haven         | 1922-01-12 | Experienced           |
| 8450257   | Jim Pavese       | New York City     | 1962-06-08 | Experienced           |
| 8450611   | Ken Quinney      | New Westminster   | 1965-05-23 | Experienced           |
| 8451224   | Mathieu Schneider| New York City     | 1969-06-12 | Experienced           |
| 8452278   | Michael Walsh    | New York City     | 1962-04-03 | Experienced           |
| 8452281   | Ryan Walter      | New Westminster   | 1958-04-23 | Experienced           |
| 8452453   | Rod Willard      | New Liskeard      | 1960-05-01 | Experienced           |
| 8452557   | Terry Yake       | New Westminster   | 1968-10-22 | Experienced           |
| 8455965   | Bobby Crawford   | New York City     | 1960-05-27 | Experienced           |
| 8456120   | Justin Duberman  | New Haven         | 1970-03-23 | Experienced           |
| 8457083   | Lonnie Loach     | New Liskeard      | 1968-04-14 | Experienced           |
| 8458579   | Nathan LaFayette | New Westminster   | 1973-02-17 | Experienced           |
| 8459028   | Marc Lamothe     | New Liskeard      | 1974-02-27 | Experienced           |
| 8459615   | Eric Boguniecki  | New Haven         | 1975-05-06 | Experienced           |
| 8460654   | Colin Forbes     | New Westminster   | 1976-02-16 | Experienced           |
| 8465005   | Colin White      | New Glasgow       | 1977-12-12 | Experienced           |
| 8465024   | Jon Sim          | New Glasgow       | 1977-09-29 | Experienced           |
| 8465914   | Francis Bouillon | New York City     | 1975-10-17 | Experienced           |
| 8466381   | Derrick Walser   | New Glasgow       | 1978-05-12 | Experienced           |
| 8467564   | Matt Hussey      | New Haven         | 1979-05-28 | Experienced           |
| 8468153   | Kevin Colley     | New Haven         | 1979-01-04 | Experienced           |
| 8468427   | Brian Pothier    | New Bedford       | 1977-04-15 | Experienced           |
| 8469653   | Jordan Sigalet   | New Westminster   | 1981-02-19 | Experienced           |
| 8470605   | Hugh Jessiman    | New York City     | 1984-03-28 | Experienced           |
| 8474031   | Kevin Shattenkirk| New Rochelle      | 1989-01-29 | Experienced           |
| 8474068   | Kyle Turris      | New Westminster   | 1989-08-14 | Experienced           |
| 8474157   | Max Pacioretty   | New Canaan        | 1988-11-20 | Experienced           |
| 8475455   | Brenden Dillon   | New Westminster   | 1990-11-13 | Experienced           |
| 8476283   | Alex Broadhurst  | New Lenox         | 1993-03-07 | Experienced           |
| 8476505   | Turner Elson     | New Westminster   | 1992-09-13 | Experienced           |
| 8477454   | Adam Erne        | New Haven         | 1995-04-20 | Young                 |
| 8477816   | Michael Zalewski | New Hartford      | 1992-08-18 | Experienced           |
| 8480835   | Jack Drury       | New York          | 2000-02-03 | Young                 |
| 8480860   | Kevin Bahl       | New Westminster   | 2000-06-27 | Young                 |
| 8480891   | Michael Kesselring| New Hampton      | 2000-01-13 | Young                 |

### Q4. Classify and count players into 'Tall' and 'Short' category based on their height where a player is tall if they are 72 inches or more. Give the total count with the classification.<br/>

| Player_Count | Classification |
|--------------|----------------|
| 10           | No Data        |
| 3847         | Tall           |
| 4634         | Short          |

### Q5. Write a query to rank the maximum average weight of the position types who are either from Toronto or Manitoba in all the years.<br/>

| Avg_Weight | Position   | Avg_Weight_Rank |
|------------|------------|-----------------|
| 89.2       | defensemen | 1               |
| 86.2       | forwards   | 2               |
| 83.5       | goalies    | 3               |

### Q6. Write queries for a running total on yearly basis and for every month since the start.<br/>
### This gives us the monthly running total on yearly basis and resets every year.<br/>

| year | month | birth_count |
|------|-------|-------------|
| 1991 | 1     | 32213       |
| 1991 | 2     | 62558       |
| 1991 | 3     | 97427       |
| 1991 | 4     | 132825      |
| 1991 | 5     | 169196      |
| 1991 | 6     | 203574      |
| 1991 | 7     | 239010      |
| 1991 | 8     | 273431      |
| 1991 | 9     | 307841      |
| 1991 | 10    | 340933      |
| 1991 | 11    | 371699      |
| 1991 | 12    | 403816      |
| 1992 | 1     | 31982       |
| 1992 | 2     | 63554       |
| 1992 | 3     | 98526       |
| 1992 | 4     | 133791      |
| 1992 | 5     | 169887      |
| 1992 | 6     | 203719      |
| 1992 | 7     | 238979      |
| 1992 | 8     | 271949      |
| 1992 | 9     | 305658      |
| 1992 | 10    | 337846      |
| 1992 | 11    | 368011      |
| 1992 | 12    | 399109      |
| 1993 | 1     | 31031       |
| 1993 | 2     | 60632       |
| 1993 | 3     | 94971       |
| 1993 | 4     | 129167      |
| 1993 | 5     | 164024      |
| 1993 | 6     | 197521      |
| 1993 | 7     | 231529      |
| 1993 | 8     | 264297      |
| 1993 | 9     | 297521      |
| 1993 | 10    | 328857      |
| 1993 | 11    | 358439      |
| 1993 | 12    | 389037      |
| 1994 | 1     | 30310       |
| 1994 | 2     | 59552       |
| 1994 | 3     | 93707       |
| 1994 | 4     | 126935      |
| 1994 | 5     | 161511      |
| 1994 | 6     | 195218      |
| 1994 | 7     | 228976      |
| 1994 | 8     | 261995      |
| 1994 | 9     | 294706      |
| 1994 | 10    | 325743      |
| 1994 | 11    | 355725      |
| 1994 | 12    | 386243      |
| 1995 | 1     | 30006       |
| 1995 | 2     | 59082       |
| 1995 | 3     | 92530       |
| 1995 | 4     | 124295      |
| 1995 | 5     | 158888      |
| 1995 | 6     | 191943      |
| 1995 | 7     | 225282      |
| 1995 | 8     | 258096      |
| 1995 | 9     | 290704      |
| 1995 | 10    | 321511      |
| 1995 | 11    | 350281      |
| 1995 | 12    | 378685      |
| 1996 | 1     | 29435       |
| 1996 | 2     | 58278       |
| 1996 | 3     | 90094       |
| 1996 | 4     | 121928      |
| 1996 | 5     | 155078      |
| 1996 | 6     | 186446      |
| 1996 | 7     | 218939      |
| 1996 | 8     | 250273      |
| 1996 | 9     | 281201      |
| 1996 | 10    | 311145      |
| 1996 | 11    | 338529      |
| 1996 | 12    | 366833      |
| 1997 | 1     | 28473       |
| 1997 | 2     | 55094       |
| 1997 | 3     | 85190       |
|......|.......|............ |
| 2021 | 10    | 312095      |
| 2021 | 11    | 341525      |
| 2021 | 12    | 370155      |
| 2022 | 1     | 28557       |
| 2022 | 2     | 54803       |
| 2022 | 3     | 83588       |
| 2022 | 4     | 112061      |
| 2022 | 5     | 142432      |
| 2022 | 6     | 172540      |
| 2022 | 7     | 203862      |
| 2022 | 8     | 235568      |
| 2022 | 9     | 266040      |
| 2022 | 10    | 295711      |
| 2022 | 11    | 324139      |
| 2022 | 12    | 351679      |

### This gives us the running total on yearly and monthly basis since the start.<br/>

| year | month | birth_count |
|------|-------|-------------|
| 1991 | 1     | 32213       |
| 1991 | 2     | 62558       |
| 1991 | 3     | 97427       |
| 1991 | 4     | 132825      |
| 1991 | 5     | 169196      |
| 1991 | 6     | 203574      |
| 1991 | 7     | 239010      |
| 1991 | 8     | 273431      |
| 1991 | 9     | 307841      |
| 1991 | 10    | 340933      |
| 1991 | 11    | 371699      |
| 1991 | 12    | 403816      |
| 1992 | 1     | 435798      |
| 1992 | 2     | 467370      |
| 1992 | 3     | 502342      |
| 1992 | 4     | 537607      |
| 1992 | 5     | 573703      |
| 1992 | 6     | 607535      |
| 1992 | 7     | 642795      |
| 1992 | 8     | 675765      |
| 1992 | 9     | 709474      |
| 1992 | 10    | 741662      |
| 1992 | 11    | 771827      |
| 1992 | 12    | 802925      |
| 1993 | 1     | 833956      |
| 1993 | 2     | 863557      |
| 1993 | 3     | 897896      |
| 1993 | 4     | 932092      |
| 1993 | 5     | 966949      |
| 1993 | 6     | 1000446     |
| 1993 | 7     | 1034454     |
| 1993 | 8     | 1067222     |
| 1993 | 9     | 1100446     |
| 1993 | 10    | 1131782     |
| 1993 | 11    | 1161364     |
| 1993 | 12    | 1191962     |
| 1994 | 1     | 1222272     |
| 1994 | 2     | 1251514     |
| 1994 | 3     | 1285669     |
| 1994 | 4     | 1318897     |
| 1994 | 5     | 1353473     |
| 1994 | 6     | 1387180     |
| 1994 | 7     | 1420938     |
| 1994 | 8     | 1453957     |
| 1994 | 9     | 1486668     |
| 1994 | 10    | 1517705     |
| 1994 | 11    | 1547687     |
| 1994 | 12    | 1578205     |
| 1995 | 1     | 1608211     |
| 1995 | 2     | 1637287     |
| 1995 | 3     | 1670735     |
| 1995 | 4     | 1702500     |
| 1995 | 5     | 1737093     |
| 1995 | 6     | 1770148     |
| 1995 | 7     | 1803487     |
| 1995 | 8     | 1836301     |
| 1995 | 9     | 1868909     |
| 1995 | 10    | 1899716     |
| 1995 | 11    | 1928486     |
| 1995 | 12    | 1956890     |
| 1996 | 1     | 1986325     |
| 1996 | 2     | 2015168     |
| 1996 | 3     | 2046984     |
|..... |...... |..........   |
| 2022 | 5     | 11535467    |
| 2022 | 6     | 11565575    |
| 2022 | 7     | 11596897    |
| 2022 | 8     | 11628603    |
| 2022 | 9     | 11659075    |
| 2022 | 10    | 11688746    |
| 2022 | 11    | 11717174    |
| 2022 | 12    | 11744714    |

### Q7. Write a query to calculate the Body Mass Index for each player with their Id, name, team, height, weight, and BMI as per their last match.<br/>


Here is the data formatted as a markdown table:


| Player_Id | Player_Name         | Team                   | Height | Weight | BMI   |
|-----------|---------------------|------------------------|--------|--------|-------|
| 8444854   | Reg Abbott          | Montréal Canadiens     | 1.8    | 74     | 22.84 |
| 8444864   | Rudy Ahlin          | Chicago Blackhawks     | 1.8    | 80     | 24.69 |
| 8444869   | Claire Alexander    | Vancouver Canucks      | 1.85   | 79     | 23.08 |
| 8444882   | Earl Anderson       | Boston Bruins          | 1.85   | 84     | 24.54 |
| 8444892   | Thommy Abrahamsson  | Hartford Whalers       | 1.88   | 84     | 23.77 |
| 8444929   | Ron Anderson        | Washington Capitals    | 1.78   | 75     | 23.67 |
| 8444947   | Perry Anderson      | San Jose Sharks        | 1.85   | 102    | 29.8  |
| 8444957   | Shawn Anderson      | Philadelphia Flyers    | 1.85   | 91     | 26.59 |
| 8444966   | John Arbour         | St. Louis Blues        | 1.8    | 88     | 27.16 |
| 8444970   | Bob Armstrong       | Boston Bruins          | 1.85   | 86     | 25.13 |
|...........|.....................|........................|....... |........|.......|
| 8482222   | Alexander Barabanov | San Jose Sharks        | 1.78   | 88     | 27.77 |
| 8482250   | Callahan Burke      | Colorado Avalanche     | 1.78   | 83     | 26.2  |
| 8482259   | Bobby McMann        | Toronto Maple Leafs    | 1.88   | 95     | 26.88 |
| 8482399   | Billy Sweezey       | Columbus Blue Jackets  | 1.85   | 93     | 27.17 |
| 8482516   | Matthew Kessel      | St. Louis Blues        | 1.88   | 93     | 26.31 |
| 8482660   | Kent Johnson        | Columbus Blue Jackets  | 1.83   | 81     | 24.19 |
| 8483460   | David Jiricek       | Columbus Blue Jackets  | 1.93   | 94     | 25.24 |
| 8483515   | Juraj Slafkovsky    | Montréal Canadiens     | 1.91   | 104    | 28.51 |
| 8483641   | Anton Levtchi       | Florida Panthers       | 1.83   | 84     | 25.08 |
| 8484125   | Hunter McKown       | Columbus Blue Jackets  | 1.85   | 93     | 27.17 |
| 8484153   | Leo Carlsson        | Anaheim Ducks          | 1.91   | 88     | 24.12 |
| 8484166   | Adam Fantilli       | Columbus Blue Jackets  | 1.88   | 88     | 24.9  |
| 8484287   | Cole McWard         | Vancouver Canucks      | 1.85   | 87     | 25.42 |

#### There are 9135 rows in total.<br/>

### Q8. What were the average height, weight, BMI of all the teams for the year 1947.<br/>

| Team_Name          | Avg_Team_Height | Avg_Team_Weight | Avg_Team_BMI |
|--------------------|------------------|------------------|--------------|
| Boston Bruins      | 1.79             | 80.6             | 25.03        |
| Chicago Blackhawks | 1.78             | 78.91            | 24.98        |
| Detroit Red Wings  | 1.79             | 80.56            | 25.1         |
| Montréal Canadiens | 1.78             | 77.38            | 24.52        |
| New York Rangers   | 1.78             | 78.89            | 24.87        |
| Toronto Maple Leafs| 1.8              | 80.36            | 24.73        |

### Q9. Categorise and count the atheletes into underweight, healthy, overweight and obese according to their BMI.<br/>

### Q9. Categorise and count the athletes into underweight, healthy, overweight, and obese according to their BMI.<br/>

| Count_Total | Category  |
|-------------|-----------|
| 2261        | Healthy   |
| 77          | Obese     |
| 6582        | Overweight|





