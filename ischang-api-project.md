---
title: GetMyWeather API Documentation
---

# GetMyWeather API Documentation

The getWeather API allows you to embed a micro-forecast into HTML pages or web apps so you can show the weather forecast for any location at a point in time. Data is returned in HTML format. 

- [Initialize the API](#initialize-the-api)
- [Make a Call](#make-a-call)
- [Display the Result](#display-the-result)
- [Methods](#methods)
- [Parameters](#parameters)
- [Possible Error Codes](#possible-error-codes)

### Initialize the API
Initialize the API by running the code:   
```html
<script type="text/javascript">
var weatherForecast;
function init() {
weatherForecast = 
 new getWeather(document.getElementById('forecast')}
</script>
```

### Make a Call
First, [register for an API key](https://getmyweather.com). All cost information can be found online, including a no-cost option for API testing.

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

### Display the Result
Insert the following element where you want to display the forecast:  
```
<div id="forecast"></div>
```
When you make a call, the getWeather API returns an HTML structure in the element similar to the example:
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
- Trust is returned as a signifier of the reliability of the forecast, with 1 being very unreliable and 100 being absolutely reliable. Wider radiuses and forecasts greater than 10 days in advance have lower trust values than specific locations close in time. Trust values less than 10 are based on historical averages for the location.  
### Methods
|Method| Description |
|------|-------------|
|Get   | The getWeather API returns the weather forecast for a specified location and time |

### Parameters

| Input       | Required/Optional | Description|
|-------------|----------|---------------------|
| Location    | Required | Geographical coordinates for latitude and longitude. This parameter should be entered in ISO 6709 format.|  
| Specificity | Required | Specificity describes how wide of a radius you want to include in your search. The minimum value is 10 meters; the maximum value is 100,000 meters.            |
| Time        | Required | Time describes when you want the weather forecasted. This parameter must be in the future and entered as hours, where decimals are allowed (e.g. 2.75 hours).|
|Key          | Required | The API key is provided by GetMyWeather when you register to use the API.|  

### Possible Error Codes

- **Invalid Key**: The API key is not valid. Check your existing key or register for a new one.
- **Invalid Parameter Format**: One or more parameters is formatted incorrectly. Check each parameter is formatted correctly. 
- **Parameter out of range**: One or more parameters is outside of its allowable range. Check each parameter is within its range.
- **Server unavailable**: The server is temporarily unavailable. Try again later.
