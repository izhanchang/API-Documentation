---
title: GetMyWeather API Documentation
---

# Get My Weather

The getWeather API allows you to embed a micro-forecast into an HTML page or web apps so you can show the weather forecast for any location at a point in time. Data is available in HTML format. 

- [Prepare the Website](#prepare-the-website)
- [Make an API Call](#make-an-api-call)
- [Methods](#methods)
- [Parameters](#parameters)
- [Possible Error Codes](#possible-error-codes)

### Prepare the website
Before running the getWeather API, you must first include an empty element for the return package to insert into. 
On the HTML page, insert the following element:
```
<div id="forecast"></div>
``` 
Then, initialize getWeather by running the code:
```html
<script type="text/javascript">
var weatherForecast;
function init() {
weatherForecast = 
 new getWeather(document.getElementById('forecast')}
</script>
```

### Make an API Call
Before making an API call, [register for an API key](https://getmyweather.com). All cost information can be found online, including a no-cost option for API testing.

After getting an API key, run the following to call getWeather:

```html
<script async defer   src="https://www.getmyweather.com/getWeather?
key=<YOUR_KEY>&
callback=init&
location=<LATITUDE>:<LONGITUDE>&
specificity=<SPECIFICITY>&
time=<TIME>">
</script>
```
If successful, the getWeather API returns an HTML structure similar to the example:
```html
<div class="forecast">
	<div class="temperature">78</div>
	<div class="windspeed">15</div>
	<div class="chanceRain">30</div>
	<div class="trust">80</div>
</div>
```
- Temperature is returned in degrees Fahrenheit.
- Windspeed is returned in miles per hour.
- ChanceRain is returned as a percentage chance.
- Trust is returned as a signifier of the reliability of the forecast, with 1 being very unreliable and 100 being absolutely reliable.  
### Methods
|Method| Description |
|------|-------------|
|Get   | The getWeather API returns the weather forecast for a specified location and time |

### Parameters

| Input       | Required/Optional | Description|
|-------------|----------|---------------------|
| Location    | Required | Geographical coordinates for latitudeand longitude. This parameter should be entered in ISO 6709 format.|  
| Specificity | Required | Specificity describes how wide of a radius you want to include in your search. The minimum value is 10 meters; the maximum value is 100,000 meters.            |
| Time        | Required | Time describes when you want the weather forecasted. This parameter must be in the future and entered as hours in decimal format (e.g. 2.75 hours)|
|Key          | Required | The API key is provided by GetMyWeather when you register to use the API.|  

### Possible Error Codes

- **Invalid Key**: The API key is not valid. Please check your existing key or register for a new one.
- **Invalid Parameter Format**: One or more parameters is formatted incorrectly. Please check if each parameter is formatted according to the specified format.
- **Parameter out of range**: One or more parameters is outside of its allowable range. Please check each parameter is within its range.
- **Server unavailable**: The server is temporarily unavailable. Please try again later.
