# Assignment3Part1
## API Description  
The Lake Manitoba API allows researchers or developers to find statistics about any lake within the province of Manitoba. This API can provide a series of data, including accurately reported temperatures, depths, Ph, and water levels since the year 2000. All statistics are recorded daily from all lakes in Manitoba, through sampling and measurement reports. 

## Endpoints and Parameters

### Endpoints: __/lake__
#### List of query parameters:  

|Name|Type|Input Format |Request|
| ---- | ---- | ---- | ---- |
|lat |integer | -90 to 90| **Required**|
|long |integer | -180 to 180| **Required**|
|Date |String |MM-DD-YYYY (Today's date by default)| *Optional*|
|System |String| 0 or 1 (1 by default). 1 for Metric system (Celsius/Meters), 0 for Imperial (Fahrenheit/Feet). |*Optional*|

### Endpoints: __/lake/lakeName__
  
|Name|Type|Input Format |Request|
| ---- | ---- | ---- | ---- |
|lakeName |String |lakeName| **Required**|
|Date |String |MM-DD-YYYY (Today's date by default)| *Optional*|
|System |String| 0 or 1 (1 by default). 1 for Metric system (Celsius/Meters), 0 for Imperial (Fahrenheit/Feet). |*Optional*|

#### Return parameters:

|Name|Type|Description|
| ---- | ---- | ---- |
|id|String|ID of specific marine body
|name|String|Returning the name of the body of water
|lat|Floating Point|Latitude of the lake you are getting information for
|long|Floating Point|Longitude of the lake you are getting information for
|water level |String (2 decimals)|Average level of water relative to itself
|depth |String (2 decimals)|Average depth of the water
|temperature |String (1 decimal)|Average temperature of the water body
|altitude |Integer|Average altitude of the body of water
|pH value |String|Average pH value of water body
|msg|String|Success or failure of response

#### Request format:
##
    lake/{lakeName}?date=MM-DD-YYYY&system={0or1}
    
    lakeName is the name of the lake you are getting information for
    
    lake?lat={value}&long={value}&date=MM-DD-YYYY&system={0or1}
    
    Latitude and longitude are the coordinates for the lake that you would like information for.

## Resources (Formatted as JSON)  

A response is received as:
##
```
{
      "results":
      {
            "id":"CA6505_1"
            "name":"lake Manitoba",
            "lat":"-83",
            "long":"111",
            "water level":"10.01",
            "depth":"13.05",
            "temperature":"15.0",
            "altitude":231,
            "pH value":"7.48"
            "msg":"The query is successful!"
      }
}
```

## Sample Request and Response 

Examples:

To receive statistics about the Red River on November 19th, 2000:
##
    lake/LakeManitoba?date=11-19-2000
    
Returns:
    
    { "results" : {"id":"CA6505_1","name":"Lake Manitoba","lat":54.668079,"long":-101.542809, "water level":"0.68", "depth":"10.09", "temperature":"17.0", "altitude":231, "pH value":"7.48", "msg": "The query is successful!"}
    
Modifying the parameters into the imperial system or using lake endpoint with latitude and longitude coordinates:
##
    lake/LakeManitoba?date=11-19-2000&system=0
    lake?lat=54.668079&long=-101.542809&date=11-19-2000&system=0
    
Both queries return:

    { "results" : {"id":"CA6505_1","name":"Lake Manitoba", "lat":54.668079,"long":-101.542809, "water level":"2.23", "depth":"33.10", "temperature":"62.6", "altitude":758, "pH value":"7.48", "msg": "The query is successful!"}

