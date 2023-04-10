---
title: GetMyWeather API Documentation
---

# Get My Weather

The Get My Weather API allows you to embed a micro-forecast into an HTML page or web apps so you can show the weather forecast for specific locations at a point in time. 

 
- [Make an API Call](#Make an API Call)
- [Know Usage and Limits](#Know Usage and Limits)
- [Communications](#communications)
- [Media](#media)
- [Miscellaneous](#miscellaneous)

## Make an API Call

### Parameters

Parameters | 
------------
```
LATITUDE
```
: Required
------------
```
LONGITUDE
```
: Required
------------
```
SPECIFICITY
```
: Required
------------
```
TIME
```
: Required 
### Example API Call
```
<script async defer   src="https://www.getmyweather.com/getWeather?
key=<YOUR_KEY>&
callback=init&
location=<LATITUDE>:<LONGITUDE>&
specificity=<SPECIFICITY>&
time=<TIME>">
</script>
```

### Example Return Package
``` html
<div class="forecast">
	<div class="temperature">78</div>
	<div class="windspeed">15</div>
	<div class="chanceRain">30</div>
	<div class="trust">80</div>
</div>
```

### Possible Error Codes
**Bad Request**: Something is wrong in the API request. Please check data and formatting in the call.

## Know Usage and Limits
Users are limited to 1000 free calls a day. After 1000 calls, users will be charged for each additional call.
