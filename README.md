# Assignment3Part1
## API Description  
The Water Body Manitoba API allows researches or developers to find statistics about any river or lake within Manitoba.
provided are accurately reported temperatures, a geodetic metric and water levels since the year 2000.

## Endpoints and Parameters

EndPoints:
- Type of the body of water (river or lake)
- Name of the river or lake in Manitoba

List of query parameters:  

|Name|Type|Input Format |Request|
| ---- | ---- | ---- | ---- |
|BodyType |String |String| ***Required***|
|WaterBodyName |String |String| ***Required***|
|Date |String |MM-DD-YYYY| ***Required***|
|System |String| 0 or 1 (1 by default)|*Optional*|

notes: 0 for Fahrenheit/feet, 1 for celsius/meters.

Return parameters:

|Name|Type|Description|
| ---- | ---- | ---- |
|msg|String|operation step
|water name| String |name of body of water
|temperature |String|temperature of water body
|water level |String|level of water relative to itself
|geodetic metric|String|
|altitude |String|altitude of the body of water
|pH value |String|average pH value of water body

Request format:
##
    BodyType/WaterBodyName?date=MM-DD-YYYY
    
The body type is either a river or lake.

## Resources (Formatted as JSON)  

A response is received as:
##
```
{
      {
            "Type":"River",
            "water name":"Red River",
            "temperature":"15",
            "water level":"10.01",
            "geodetic metric":"222.01",
            "altitude":"231",
            "pH value":"7.48"
      },
      "msg":"The query is successful!"
}
```

## Sample Request and Resposnse 

Example:

To receive statistics about the Red River on November 19th, 2000:
##
    river/redriver?date=11-19-2000
    
Returns:
    
    {"water name":"Red River", "water level":"0.68", "temperature":"17", "geodetic Metric":"222.01", "altitude":"231", "pH value":"7.48"}
    
Modifying the parameters into the imperial system:
##
    river/redriver?date=11-19-2020&system=0
    
Returns:

    {"water name":"Red River", "water level":"2.23", "temperature":"62.6","geodetic Metric":"728.37", "altitude":"758", "pH value":"7.48"}
