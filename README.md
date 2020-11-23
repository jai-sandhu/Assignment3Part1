# Assignment3Part1
## API Description  
The Water Body Manitoba API allows researches or developers to find statistics about any river or lake within Manitoba.
We provide accurately reported temperatures, a geodetic metric and water levels since the year 2000.

## Endpoints and Parameters

EndPoints:
- Type of the body of water (river or lake)
- Name of the river or lake in Manitoba

List of query parameters:  

|Name|Type|Input Format |Request|
| ---- | ---- | ---- | ---- |
|date |String |MM-DD-YYYY| ***Required***|
|temperature |String| 0 or 1 (1 by default)|*Optional*|
|water level |String| 0 or 1 (1 by default)|*Optional*|

notes: 0 for Fahrenheit/feet, 1 for celsius/meters.

Return parameters:

|Name|Type|Description|
| ---- | ---- | ---- |
|msg|String|operation step
|water name| String |
|temperature |String|temperature of water body
|water level |String|
|geodetic metic|String|
|altitude |String|water's altitude
|pH value |String|

Request format:
##
    BodyType/WaterBodyName?date=MM-DD-YYYY&temperature={0or1}&waterLevel={0or1}
    
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
    river/redriver?date=11-19-2020
    
Returns:
    
    {"water name":"Red River", "water level":"0.68", "temperature":"17", "geodetic Metric":"222.01", "altitude":"231", "pH value":"7.48"}
    
Modifying the parameters into the imperial system:
##
    river/redriver?date=11-19-2020&temperature=0&waterLevel=0&geodetic=0
    
Returns:

    {"water name":"Red River", "water level":"2.23", "temperature":"62.6","geodetic Metric":"728.37", "altitude":"758", "pH value":"7.48"}
