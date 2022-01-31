# Project: Data Modeling with Postgres

## Objective :
      Build a star schema data model in Postgres. 
      Build the ETL pipeline in Python to transfer the data files from local directories into the fact and dimension tables.

### Dataset
    The data is available in **2 differernt JSON files**.
    
    **1. Song Dataset :**
            * Contains metadata about a song and the artist of that song. 
            * Multiples files.
            * The files are partitioned by the first three letters of each song's track ID.
             
     **2. Log Dataset:**
            * Contains the activity log - like the duration of the song, user info, session info etc.
            * Multiple Files
            * The files are partitioned by year and month.

### Brainstorming/Whiteboarding :

      A closer look at the dataset reveals that most of the info for the DIMENSION table is in the Song dataset. The log dataset however, contains a mix of both DIMENSION data ( TIME Dimension) and FACT data.
      
### Process Steps :

**Step 1 :**
    Identify the data entities and group them into FACT and Dimensions.
    
    ** Fact : **
    
     Song_Play
    
    **Dimensions :**
      
       Users 
       Songs
       Artists
       Time
       
    
