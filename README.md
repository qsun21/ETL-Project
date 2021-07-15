ETL-Project
  
  
    Team member: Mario Shields and Qian Sun
    projectwork notebook: CombinedETL.pynb


  Background


  The Chicago Park District collects and analyzes water samples from beaches along Chicago’s Lake Michigan lakefront. The Chicago Park District partners with the                 University of Illinois at Chicago Department of Public Health Laboratory to analyze water samples using a new DNA testing method called Rapid Testing Method (qPCR               analysis) which tests for Enterococci in order to monitor swimming safety.

  The rapid testing method (qPCR analysis) is a new method that measures levels of pathogenic DNA in beach water. Unlike the culture based test that requires up to 24              hours of processing, the new rapid testing method requires a 4-5 hours for results. The Chicago Park District can use results of the rapid test to notify the public when        levels exceed UPEPA recommended levels, which is 1000* CCE. When DNA bacteria levels exceed 1000 CCE, a yellow swim advisory flag is implemented. For more information          please refer to the USEPA Recreational Water Quality Criteria. 


  The goal of this project
  
  This project aims to store below data resources in SQL database in order to measure correlation between bacteria levels found on different beaches and beach temperature         going forward.
  
  
  1.Extract/Data Utilized
   
    Web resource  
   
    Weather Stations- csv file data    
    https://data.cityofchicago.org/Parks-Recreation/Beach-Weather-Stations-Automated-Sensors/k7hf-8y75/
    
    Beach Lab Data- Json data 
    https://catalog.data.gov/it/dataset/beach-lab-data\n 


  We obtain data from two sources, execute an ETL workflow, and finally store the data to a Postgres database
  Qian Sun part includes calling an API to extract json data describing bacteria levels on a given beach.
  Mario's part includes calling CSV data data describing temperature levels on a given beach 


2.Transformation

  Json data extracted used the requests module to get the json from the web source, and it was turned into a dictionary and parsed each row of data into a column                 format in order to be able to load it into a Pandas dataframe. CSV file data extracted by pandas reading the Beach stations weather data into dataframe. Then 2                  postgres tables were automatically created by calling the to_sql method on my Pandas dataframe.
  

3.Load
  
  All of the data was uploaded into a relational database with Postgres. The database had 2 main tables for use: 1) beachlab  2)  beachweather. 
  Two tables were able to joining and display data correctly.
   
 
