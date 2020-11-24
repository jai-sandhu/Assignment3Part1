# Assignment3Part1
## API Description  
The Water Body Manitoba API allows researchers or developers to find statistics about any river or lake within Manitoba.
provided are accurately reported temperatures, a geodetic metric, and water levels since the year 2000.

## Endpoints and Parameters

#### Endpoints:
- Type of the body of water (river or lake)
- Name of the river or lake in Manitoba

#### List of query parameters:  

|Name|Type|Input Format |Request|
| ---- | ---- | ---- | ---- |
|Date |String |MM-DD-YYYY (Today's by default)| *Optional*|
|System |String| 0 or 1 (1 by default). 1 for Metric system (Celsius/Meters), 0 for Imperial (Fahrenheit/Feet). |*Optional*|

#### Return parameters:

|Name|Type|Description|
| ---- | ---- | ---- |
|msg|String|Success or failure of response
|name|String|Returning the name of the body of water
|water level |String (2 decimals)|Average level of water relative to itself
|depth |String (2 decimals)|Average depth of the water
|geodetic metric|String (2 decimals)|Geodetic measurement of water
|temperature |String (1 decimal)|Average temperature of the water body
|altitude |Integer|Average altitude of the body of water
|pH value |String|Average pH value of water body

#### Request format:
##
    BodyType/WaterBodyName?date=MM-DD-YYYY&system={0or1}
    
BodyType is either a river or a lake.

WaterBodyName defines the name of the river or lake.

## Resources (Formatted as JSON)  

A response is received as:
##
```
{
    "results":
      {
            "name":"Red River",
            "water level":"10.01",
            "depth":"13.05",
            "geodetic metric":"222.01",
            "temperature":"15.0",
            "altitude":231,
            "pH value":"7.48"
      },
      "msg":"The query is successful!"
}
```

## Sample Request and Response 

Example:

To receive statistics about the Red River on November 19th, 2000:
##
    river/redriver?date=11-19-2000
    
Returns:
    
    { "results" : {"water name":"Red River", "water level":"0.68", "depth":"10.09", "temperature":"17.0", "geodetic Metric":"222.01", "altitude":231, "pH value":"7.48"}, "msg": "The query is successful!"}
    
Modifying the parameters into the imperial system:
##
    river/redriver?date=11-19-2000&system=0
    
Returns:

    { "results" : {"water name":"Red River", "water level":"2.23", "depth":"33.10","temperature":"62.6","geodetic Metric":"728.37", "altitude":758, "pH value":"7.48"}, "msg": "The query is successful!"}
