# Project: Data Modeling with Postgres

## Objective :
      * The main of Sparkify is to understand users choice of songs, in other words they want to understand what songs they are listening to. 
      * Build a star schema data model in Postgres for Sparkify to analyze the songs and User activity data collected on their music  streaming app. 
      * Build the ETL pipeline in Python to transfer the data files from local directories into the fact and dimension tables.
      
      
### Dataset
    The data is available in 2 differernt JSON files.
    
    1. Song Dataset :
            * Contains metadata about a song and the artist of that song. 
            * Multiples files.
            * The files are partitioned by the first three letters of each song's track ID.
             
     2. Log Dataset:
            * Contains the activity log - like the duration of the song, user info, session info etc.
            * Multiple Files
            * The files are partitioned by year and month.

### Database Schema Design  :

      A closer look at the dataset reveals that most of the info for the DIMENSION table is in the Song dataset. The log dataset however, contains a mix of both DIMENSION data ( TIME Dimension) and FACT data. The Process Steps defined below explain how we designed the Star schema.
      
### Process Steps :

**Step 1 :**
    Identify the data entities and group them into FACT and Dimensions.
    Identify attributes that belong to the fact and dimension tables.
    
    Fact :
    
     Song_Play : 
          * songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
    
    Dimensions :
      
       Users   : user_id, first_name, last_name, gender, level
       Songs   : song_id, title, artist_id, year, duration
       Artists : artist_id, name, location, latitude, longitude
       Time    : start_time, hour, day, week, month, year, weekday
       
    
 **Step 2:**
 
 **Create Tables**
   
   * The DROP (if table exixsts) and CREATE statements are written in the sql_queries.py
   
   * In the project workspace navigate to File-->New-->Terminal 
     or select the Terminal shortcut from the launcher space under the 'Other' section.
   
   * Type in python create_tables.py
   
   * This command will trigger the create statements in the sql_queries.py file.
   
   * Run test.ipynb to confirm the creation of your tables with the correct columns.
 
 **Step 3:**
 
 **Build ETL Process**
 
      * etl.ipynb contains the process the ETL process to populate the star schema.
      
      * Test the ETL Process by running the test.ipynb to check if the tables contain the correct data.
      
 **Step 4:**
 
 **Build ETL Pipeline**
      
      The etl.py file contains the ETL process developed in step 3 and will process the entire dataset and populate the star schema.
      
      This file can be triggered by running the command 'python etl.py' in the terminal.
      
      
