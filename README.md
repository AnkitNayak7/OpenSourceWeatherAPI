# OpenSourceWeatherAPI

[![Version](https://img.shields.io/badge/version-v1.0.0-brightgreen.svg)](https://github.com/your-username/open-weather-api/releases/tag/v1.0.0)
[![Build Status](https://travis-ci.org/your-username/open-weather-api.svg?branch=main)](https://travis-ci.org/your-username/open-weather-api)
[![Documentation](https://img.shields.io/badge/docs-yes-success.svg)](https://your-username.github.io/open-weather-api)

## Overview
Retrieving live weather information from the open-source platform [tomorrow.io.](https://app.tomorrow.io/home), and incorporating it into a project through integration with the application.

## Features
- **Live Weather Updates:** Retrieve realtime weather details for a specified location.
- 
### Input
- **Latitude:** Latitude of the Specific Location.
- **Longitude:** Longitude of the Specific Location.
- **Unit:** Unit system of the field values, either "metric" or "imperial"
- **Access Key:** This project uses a free access key form tomorrow.io. In case of any issue create a new key from login to  [tomorrow.io-> API Managemenet](https://app.tomorrow.io/development/keys) and create a new access key.

### Limitation
**There is a limitaion from tomorrow.io, allowing only 1000 requests per day. Currently, our configuration allows for requests every 5 minutes, totaling 288 requests per day.**


### Documentation
Check out the [documentation](https://docs.tomorrow.io/reference/realtime-weather) for detailed information on API endpoints, parameters, and response formats.


### Query Request
```
import requests

url = "https://api.tomorrow.io/v4/weather/realtime?location=14.5328333%2C%20100.45363888888889&units=metric&apikey=H7lYUEAHQRHmdfu2UQw3YivHpYGtJrmn"

headers = {"accept": "application/json"}

response = requests.get(url, headers=headers)

print(response.text)
```

### Query Response
```
{
  "data": {
    "time": "2023-01-26T07:48:00Z",
    "values": {
      "cloudBase": 0.07,
      "cloudCeiling": 0.07,
      "cloudCover": 100,
      "dewPoint": 0.88,
      "freezingRainIntensity": 0,
      "humidity": 96,
      "precipitationProbability": 0,
      "pressureSurfaceLevel": 984.57,
      "rainIntensity": 0,
      "sleetIntensity": 0,
      "snowIntensity": 0,
      "temperature": 1.88,
      "temperatureApparent": -0.69,
      "uvHealthConcern": 0,
      "uvIndex": 0,
      "visibility": 9.9,
      "weatherCode": 1001,
      "windDirection": 10,
      "windGust": 3.38,
      "windSpeed": 2.38
    }
  },
  "location": {
    "lat": 43.653480529785156,
    "lon": -79.3839340209961,
    "name": "Old Toronto, Toronto, Golden Horseshoe, Ontario, Canada",
    "type": "administrative"
  }
}
```
