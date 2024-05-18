# ECSE3038 Project

## Overview
This project provides a simple smart hub API using FastAPI. The API allows users to manage environmental settings, log sensor data, and control devices like fans and lights based on user preferences and sensor inputs.

## API Functions

### `parse_time()`
- **Description**: Converts a duration string into a `timedelta` object.
- **Usage**: This function helps in handling duration inputs by converting them into a format that can be easily manipulated for time-based calculations.

### `convert24()`
- **Description**: Converts 12-hour formatted time into 24-hour formatted time.
- **Usage**: Ensures that time comparisons and calculations are consistent by standardizing time into 24-hour format.

### `sunset_calculation()`
- **Description**: Determines the actual time for sunset using an external API.
- **Usage**: Automates lighting based on natural sunset times, fetched dynamically via an API.

### `get_data()`
- **Description**: Retrieves sensor data from the database to populate the graph.
- **Usage**: Provides historical sensor data for visualization and analysis.

### `update_settings()`
- **Description**: Updates user settings in the database or creates an entry if none exists.
- **Usage**: Allows users to customize and save their environmental control preferences.

### `createSensorData()`
- **Description**: Creates a new database entry from the ESP32 sensor data.
- **Usage**: Logs temperature, presence, and timestamp data from the ESP32 device.

### `fan_control()`
- **Description**: Compares user-set temperature with the current temperature to determine if the fan should be turned on.
- **Usage**: Automates fan control based on temperature thresholds and presence data.

### `light_control()`
- **Description**: Compares the user-set start time, calculated end time, and current time to determine if the light should be turned on.
- **Usage**: Automates lighting based on user preferences, presence data, and natural sunset times.

## Embedded Functions

### `temp()`
- **Description**: Measures the temperature of the environment using the DHT11 temperature sensor.
- **Usage**: Provides real-time temperature data for environmental control and logging.

### `presence()`
- **Description**: Controls the operation of the PIR sensor to detect presence.
- **Usage**: Provides real-time presence data to automate fan and light control.

### `postSensorData()`
- **Description**: Makes a POST request to the API with sensor data as the request body.
- **Usage**: Sends collected sensor data to the API for logging and further processing.

### `getFanData()`
- **Description**: Makes a GET request to the API and uses the result to turn the fan on or off.
- **Usage**: Fetches fan control status from the API and adjusts the fan state accordingly.

### `getLightData()`
- **Description**: Makes a GET request to the API and uses the result to turn the light on or off.
- **Usage**: Fetches light control status from the API and adjusts the light state accordingly.
