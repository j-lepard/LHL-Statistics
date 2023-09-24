# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The overarching objective of this project was to perform and end-end data engineering activity, followed by statistical modelling to evaluate a hypothesis. 

**Goals included:** 
1. Developing API calls for City Bike to identify providers in a given location
2. Creating API calls  for two location-based information sources (Yelp, Foursquare) to obtain POI data
3. Incorporating results into a local database (Sqlite3)
4. Develop and test a hypothesis for relationship between POI and City Bike data 

## Process

### Step 1: Obtain detailed information about bike-share stations in Vancouver.
1. Obtain Master List of City Bike providers
Library required
2. Parse list to identify provider ID for Target City (vancouver)
3. Filter the list of network providers for one that is in the target city
4. Query City Bikes a second time to request detailed information for provider ('mobibikes')

> Details:  [01.city_bikes.ipynb](notebooks%2F01.city_bikes.ipynb)
> 
> Outcome: [city_bikes.csv](data%2Fcity_bikes.csv)


## Step 2: Create consolidated listing of POI data within a 1km radius of each Bike Station

The following steps were performed to obtain data from Foursquare. They were then repeated (revised as required) for Yelp. 
1. Create function takes lat/long and radius as arguments.
2. GET parameters include desired categories, and field information
3. API response (json) file is iterated to retrieve data (name, popularity, price etc)
4. data (dictionary) is appended to a list callled “FS_API_result”
5. List of lat/longs from CityBikes (vancouver_stations) is itererated.
6. Each lat/log in Vancouver_stations creates a new API call in the ‘foursquare’ function.
7. Results from each call (FS_API_Result) are in turn iterated and appended to the “All Results” list.
8. All_Results is a tidy dictionary that does not require json normalization.
9. DataFrame is created using All_Results dictionary.
10. DataFrame is dumped to json in ../data folder for future reference.

> Details: [02.yelp_foursquare_EDA.ipynb](notebooks%2F02.yelp_foursquare_EDA.ipynb)
> 
> Outcome:
> 
>   [FS_location_results.csv](data%2FFS_location_results.csv)\
>   [Yelp_location_results.csv](data%2FYelp_location_results.csv)

## Results
(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)

## Challenges 
(discuss challenges you faced in the project)

## Future Goals
(what would you do if you had more time?)
