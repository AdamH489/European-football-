# European-football-
I utilised SQL to query a database

I collected the data from https://www.kaggle.com/datasets/hugomathien/soccer/data and this data is in SQLite, therefore in the 'pythonProject' IDE, I connected to the SQLite database in order to query the data.

This is a large database with 25,000 matches, 10,000 players and the data was collected from the 2008 to 2016 seasons. Players and teams attributes were sourced from EA Sports' FIFA and the betting odds were from up to ten providers. With this database, I aim to showcase my SQL (specifically the SQLite implementation) skills whilst learning about the database. As a result, I won't analyse the findings of the data much but instead describe how I structured my queries to produce the output.

First of all, I imported the relvant libraries and then connected the correct path to the SQLite database file. I wanted to initally learn about what data was shown in this file so I printed a list of the tables in the database which showed the following output:

![image](https://github.com/AdamH489/European-football-/assets/122322345/1ee0c75e-a3f4-44ab-8169-7c4636ea60a1)

I would also like to know what countries are prevalent in the database so I printed the list of countries which produced the following output:

![image](https://github.com/AdamH489/European-football-/assets/122322345/04b3ac0f-329e-4d97-8549-9bf474e122e0)

Next, I joined the 'League' and 'Country' tables and I joined them based on the 'country_id' field. The output for this is shown below:

![image](https://github.com/AdamH489/European-football-/assets/122322345/5b98ee52-a63e-4018-8aa2-f523bfe45ec1)

I then retrieved a list of teams ordered by 'team_long_name' and I also want to retrieve only the first ten results. This output is shown below:

![image](https://github.com/AdamH489/European-football-/assets/122322345/5b4a2275-cf9d-41aa-a483-a22933933e3a)

Next, I wrote a SQL Query that retrieves detailed match information for matches in Spain. It joins data from the 'Match', 'Country', 'League' and 'Team' tables to produce the following output:

![image](https://github.com/AdamH489/European-football-/assets/122322345/6c351588-9687-4139-bdc9-383ff5e223af)

I then started to group the data to the levels which I wanted to examine. The query retrieves data from the 'Match', 'Country','League' and 'Team' tables. I then joined the 'Match' table with the 'Country' and 'League' tables using the corresponding IDs to get information about the country and league of each match. The query performs left joins to connect the 'Match' table with the 'Team' table twice, once for the home team (HT) and once for the away team (AT). These joins use the 'team_api_id' from the 'Match' table and the 'Team' table to retrieve the long names of the home and away teams. The WHERE clause filters the results to include only matches in the specified countries (Spain, Germany, France, Italy, England).
The results are grouped by country, league, and season using GROUP BY. The HAVING clause filters out records where the number of distinct stages is less than 10. The results are ordered by country name, league name, and season in descending order (most recent seasons first). The query produces the following output:

![image](https://github.com/AdamH489/European-football-/assets/122322345/a5b3d7fa-ad4d-4f52-bce9-d11cea5d19b8)

In matplotlib, I then produced two graphs showing average goals per game and average goals difference home vs out, over time. This output can be seen below:

![image](https://github.com/AdamH489/European-football-/assets/122322345/7eadc957-633d-4eff-b5c0-6fa0d57cb8f8)

![image](https://github.com/AdamH489/European-football-/assets/122322345/fae24de6-0fca-4305-8788-d7c21567b5b8)

I wanted to learn about the relationship between the height of a player and their potential so I produced the output given below. The query aggregates data from the 'PLAYER' and 'Player_Attributes' tables to calculate various statistics for players based on their height ranges. 

![image](https://github.com/AdamH489/European-football-/assets/122322345/40b1cc5a-6514-464e-ad66-ef11c9d6bb9d)

Utilising matplotlib, I then produced a line graph which shows how the height of the player is correlated with the potential of the players. This is shown below:

![image](https://github.com/AdamH489/European-football-/assets/122322345/d7e18273-a7dd-4903-bf7e-8219ec5b296c)






