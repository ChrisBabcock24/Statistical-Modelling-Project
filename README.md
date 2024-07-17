# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
(fill in your description and goals here)
My goal was to determine if there is any correlation between bike station availability and ratings for any business within the range of a given city
(Montreal). By making 3 separate API requests and combining the collective data into 1 DataFrame I was able to create a regression model to compare the relation of business ratings to locations of bike stations. 


## Process
### (your step 1)
Read through API for City Bikes and determine how to find a suitable city. 
Find a suitable city to reference City Bikes API. Required searching through data['networks']['id'] instead of data['networks']['location']['city']
Test basic code to find Montreal and return a latitude and longitude.
Find a way to loop through stored latitude and longitude and return the applicable information like free bikes and empty slots.
Stored the station information into a DataFrame 

### (your step 2)
### FOURSQUARE ###
Read through Foursquare API and test a simple request to retrieve restaurant information with a set latitude and longitude.
Import 'montreal_df' DataFrame stored as CSV file into Foursquare notebook. 
Use the referenced latitude and longitude for bike stations and make a request to Foursquare with this information.
Create a dictionary using extracted information then input into a DataFrame 'foursquare_df'.
Store the DataFrame as a CSV to be joined in another notebook.
### YELP ###
Read through Yelp API. Use some of the same concepts from Foursquare request and fit to Yelp request. 
Alter request to limit to the maximum requests per day. Found this out trying to run initial code, returned error 429 after limit reached and required waiting until next day. 
Use 'montreal_df' to loop through requests at corresponding latitudes and longitudes.
Store business information in a dictionary from loop and then into a DataFrame. Stored results into a CSV to be joined with Foursquare and City Bike data.

### (your step 3)
Join all 3 CSV files with stored data into a SQLite database.
Clean any data that may be duplicated or not useful. Clean any formatting that may affect results of visualization and modelling.
Joined data that matched with other tables like business name or latitude/longitude. 
Removed NULL/NaN values from data to improve statistical calculations like R Squared and P-value. 



## Results
(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)

Most of the ratings and number of ratings for Foursquare returned null values using the API documentation that I had in the Places API.
Recent changes - Venue search has been integrated into the Places API and the ratings response may not be functional?
Yelp provided all the Ratings for comparison. 

## Challenges 
(discuss challenges you faced in the project)

-Names of city do not necessarily return hit for City Bikes. I had to search manually in ID for the city name chosen (Montreal) which was part of 
BIXI-Montreal. Not standardized.

-Yelp request calls were limited to 300 per day. Foursquare had a much larger limit possibly due to the association with Lighthouse Labs account?

-Yelp Limited to using businesses for search. Was not as broad as Foursquare but had ratings for each business. In fact could only return businesses with a rating. Would not provide any without reviews. 

## Future Goals
(what would you do if you had more time?)

I would determine a functional way to return Foursquare ratings and rating counts so the data would be more accurate. 
Finding more insights that affect the rating. Finding other documentation to use in tables. 
I would find better methods to clean null values without losing a substantial amount of relevent data. 
Create a model that better explained the variance. Find other input variables.

NOTE: CHANGED API REQUESTS TO STORE THE ORIGINAL REFERENCED LATITUDE AND LONGITUDE IN DATAFRAMES TO BE ABLE TO MERGE LATER
NOTICED THIS WHEN RE-SUBMITTING PROJECT.
ALL VISUALIZATIONS MADE WERE CREATED IN THE NOTEBOOK - Visualization Exploration.ipynb
ONE EXAMPLE WAS PROVIDED IN THE ASSIGNMENT NOTEBOOK AS WELL. 
EDA PROCESS WAS PERFORMED IN NOTEBOOK eda_stats_model_Testing.ipynb
THIS WAS DONE TO BETTER ORGANIZE AND NOT CLUTTER THE MAIN NOTEBOOK PROVIDED BY THE BOOTCAMP