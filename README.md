# Assignment3Part1
## API Description  
The Water Body Manitoba API allows researches or developers to find statistics about any river or lake from within Manitoba.
We provide accurately reported temperatures, a geodetic metric and water levels since the year 2000.

## Endpoints and Parameters

EndPoints:
- Type of the body of water (river or lake)
- Name of the river or lake in Manitoba

List of query parameters:  
- date (string): The date of the statistic, MM-DD-YYYY format. ***Required***
- Temperature (integer): 0 or 1 (1 by default). 0 for fahrenheit 1 for celsius. *Optional*
- Water level (integer): 0 or 1 (1 by default). 0 for feet 1 for meters.  *Optional*
- Geodetic metic (integer): 0 or 1 (1 by default). 0 for feet 1 for meters. *Optional*

Request format:
##
    BodyType/WaterBodyName?date=MM-DD-YYYY&temperature={0or1}&waterLevel={0or1}
    
A body type is either a river or lake.

## Resources (Formatted as JSON)  

Optional parameters with the value 'false' do not return any information.

By default, optional parameters are true if not specified.

A response is received as:
##
    {
        "Name":"Red River",
        "Temperature":"15",
        "Water level":"10.01",
        "Geodetic metric":"222.01"
    }

## Sample Request and Resposnse 

Example:

To list all staticstics of a body of water on a specific day,
##
    {bodyType}/{waterBodyName}?date=01-02-2000
    

    river/redriver?date=11-19-2020
    
Return:
    
    {"name":"Red River","Water level":0.68","Geodetic metric (m)":"222.01", "date":"11-19-2020"}
