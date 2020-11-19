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



<<<<<<< HEAD
## API Description  
  This do be a description 
=======
>>>>>>> eedca42810da98190f440658eb36e598e72ad203


## API  

Leaving the endpoint as stats, we return a JSON object giving the stats of the specified lake/river.

List of query parameters:  
- date (string) in a MM-DD-YYYY format

##
    lake/{lakeName}/stats
    river/{riverName}/stats
<<<<<<< HEAD
    river/{riverName}/stats?stats1=val&stats2=val



## Resources (Formatted as JSON)  

These do be resources doe
=======
    river/{riverName}/stats?date=03-22-2019
>>>>>>> eedca42810da98190f440658eb36e598e72ad203

## Sample Request and Resposnse 
