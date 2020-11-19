# Assignment3Part1
## API Description  
The Water Body Manitoba API allows researches or developers to find statistics about any lake or river in Manitoba.
We provide accurately reported temperatures, water levels, and algae levels since the year 2000.


## API  

Leaving the endpoint as stats, we return a JSON object giving the stats of the specified lake/river.

List of query parameters:  
- date (string) in a MM-DD-YYYY format

##
    lake/{lakeName}/stats
    river/{riverName}/stats
    river/{riverName}/stats?stats1=val&stats2=val


## Resources (Formatted as JSON)  

These do be resources doe
    

## Sample Request and Resposnse 

Example:
    
    river/redriver/stats?date=11-19-2020
    
Return:
    
    {"name":"Red River","Water level":0.68","Geodetic metric (m)":"222.01", "date":"11-19-2020"}
