# Assignment3Part1

## Ideas 
- Winnipeg transit API
- Levels of minerals in various bodies of water in Manitoba (For example, Red River or Lake Winnipeg)
- Covid statistics in Manitoba
- Snow fall report API in Manitoba
- Toilets near me within Manitoba, distance and direction API
- Winnipeg Harvest, donation tracking API
- 
  
  Parameters: Name of the body of water, and a day of the month. 
  
  Returns: Statistics of that body for that day





## API  

Leaving the endpoint as stats, we return a JSON object giving the stats of the specified lake/river.

List of query parameters:  
- date (string) in a MM-DD-YYYY format

##
    lake/{lakeName}/stats
    river/{riverName}/stats
    river/{riverName}/stats?date=03-22-2019

