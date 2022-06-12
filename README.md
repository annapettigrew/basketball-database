# <NBA Player Statistics>


## EXTRACT, TRANSFORM, & LOAD - NBA PLAYER STAISTICAL DATA 
Github Repository: https://github.com/annapettigrew/project-02-group-06 <br />  
Team Members <br />
Anna Pettigrew: www.linkedin.com/in/anna-pettigrew <br />   
Ewansiha Simmons:  https://www.linkedin.com/in/ewansiha-simmons-5b7b9a1/ <br />  


## PROJECT DESCRIPTION
<p align="left">
 <br />
For this project, we utilized two databases from Kaggle.com. <br />
  Database 1: https://www.kaggle.com/datasets/wyattowalsh/basketball (large zip file linked in Resources)<br />
  Database 2: https://www.kaggle.com/datasets/justinas/nba-players-data <br />
  Database 1 is in a SQLite format and Database 2 is in a CSV format.<br />
</p>
<br />
<p align="left">
These datasets were chosen because they each contain a large repository of information for National Basketball Association (NBA) statistics for teams, players, officials, draft information, biographies, pictures and they complemented each other well. Dataset 1 has information from 1945 until 2021 and Dataset 2 has information from 1996 to 2019. Due to the nature of the data, we decided to create a relational database focusing on the players' statistics for each year they are in the NBA because the players names are in both datasets giving a natural staring point for combining the two datasets into one database.
</p>

</p>

Information included in the final merged database are: 	<br />
   PLAYER NAME, DRAFT YEAR,	NUMBER OVERALL PICK, TEAM NAME FROM,	ORGANIZATION FROM,	TEAM NAME,	SALARY,	HEIGHT,	WEIGHT,	JERSEY      NUMBER,	POSITION,	PTS,	AST,	REB,	PIE,	GAMES PLAYED,	POINTS,	REBOUNDS,	ASSISTS,	NET RATING,	SEASON
</p>
<p align="left">
The merged dataset is very useful for NBA enthusiasts and data scientists because it can be sorted by player, season, team, draft year, college, or any of the other various statistics included in the merged dataset.  In addition, utilizing the code provided, it can be manipulated further from the raw data with additional categories not included in the final dataset.  There are 302 rows and 21 columns in the final merged database.
</p>


## DATA EXTRACTION PROCESS 
 <p align="left"><br />
1.  Downloaded Database 1 and extracted data from zip file <br />
2.  Reviewed Tables and columns included in dataset via Pandas and Jupyter Notebook to determine which were most needed       for NBA Player statistics by Year. <br />
3.  Downloaded Database 2 and reviewed the csv file to determin which columns were needed for combined dataset. <br />
</p>  

## DATA TRANSFORMATION PROCESS 
<p align="left"><br />
Utilizing Jupyter Notebook Python 3(ipykernel)
Dependencies:
  sqlalchemy
  pandas 
  sqlalchemy.ext.automap import automap_base
  sqlalchemy.orm import Session
  sqlalchemy import create_engine, inspect, func
  
1.   Created an engine to connect to the baketball.sqlite db 
2.   Read in  player_attributes, player_salary, and draft tables from the SQLite file 
3.   Checked the tables to make sure they were imported properly
4.   Merged the columns from each table into a new dataframe and verified they were merged properly![Basketball_JN_1](https://user-images.githubusercontent.com/99496137/173203386-82bc6603-aaae-466f-bdf1-f04219993872.png)
5.    Created an engine to connect to the NBA_PLAYERS_1996-2019.csv![Basketball_JN_2](https://user-images.githubusercontent.com/99496137/173203802-44b23076-7ff5-44e8-b8e6-5fc60a147314.png)
6.   Reorganized the columns and renamed columns
7.   Set Index for table to 'PLAYER NAME' 
8.   Dropped other columns in dataframe that were deemed unnecessary for final database.
9.   Verified columns reflected changes by printing dataframe
10.  Filtered data for'2020-21'Season and created new season_db <br /> </p>
![Basketball_JN_4](https://user-images.githubusercontent.com/99496137/173205978-c1ea51be-f92b-4d69-a86f-7f063a2f7658.png)<br />

 
## DATA LOADING PROCESS
 <p align="left"> 
1.  Created 'new_basketball_db' in PgAdmin with no tables<br />
2.  Used rds_connection_string in Jupyter Notebook to insert 'clean_basketball_db' table and 'season_db' tables into 'new_basketball_db' <br />
3.  Reviewed Tables in PgAdmin to confirm data matched tables in Jupyter Notebook <br /> <br />

![Screen Shot 2022-06-11 at 7 09 52 PM](https://user-images.githubusercontent.com/99496137/173208753-b7918996-2132-428e-8ceb-a6450cd83fb9.png)</p> 
## FINDINGS
<p align="left"> 
1.  When constructing dataframes in Jupyter Notebook, it was helpful to rename columns before setting the table index to reduce run errors.<br />
2.  Created new dataframe after each drop, rename, other changes to eliminate run errors and not have to restart kernel in Jupyter Notebook. <br />
3.  When editing columns, It is helpful to print the dataframe to verify the accuracy of changes.<br /> 




## License
<p align="left"> 
Distributed under the MIT License. See `LICENSE.txt` for more information.
</p>


  
  
  
  
  
  
  
  
  
