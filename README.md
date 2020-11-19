# Assignment3Part1

## API Description  
The Water Body Manitoba API lets you find statistics for any lake or river in Manitoba.
Statistics we provide includes, temperature, water levels, and algae levels.


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
    river/{riverName}/stats?date=03-22-2019

## Sample Request and Resposnse 

Example:
    
    river/redriver/stats?date=11-19-2020
    
Return:
    
    {"name":"Red River","Water level":0.68","Geodetic metric (m)":222.01"}
