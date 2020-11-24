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
|Date |String |MM-DD-YYYY| ***Required***|
|System |String| 0 or 1 (1 by default). 1 for Metric system (Celsius/Meters), 0 for Imperial (Fahrenheit/Feet). |*Optional*|

Return parameters:

|Name|Type|Description|
| ---- | ---- | ---- |
|msg|String|operation step
|water name| String |Name of body of water
|water level |String (2 decimals)|Average level of water relative to itself
|geodetic metric|String (2 decimals)|Geodetic measurement of water
|temperature |Integer|Average temperature of water body
|altitude |Integer|Average altitude of the body of water
|pH value |String|Average pH value of water body
|depth|

Request format:
##
    BodyType/WaterBodyName?date=MM-DD-YYYY
    
The body type is either a river or lake.

## Resources (Formatted as JSON)  

A response is received as:
##
```
{
    "results":
      {
            "Type":"River",
            "water name":"Red River",
            "temperature":15,
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
