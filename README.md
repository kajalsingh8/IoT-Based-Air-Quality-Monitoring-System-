# Air Quality Monitoring Using Blynk, ThingSpeak, and ESP8266

This project monitors air quality using an ESP8266 microcontroller. It measures temperature, humidity, and gas concentration, displaying the data on an LCD screen and sending it to ThingSpeak for logging and Blynk for real-time monitoring and alerts.

## Project Overview

This project aims to provide real-time monitoring of air quality using a combination of sensors and cloud services. The ESP8266 microcontroller collects data from the DHT11 and MQ135 sensors, displays the information on an LCD screen, and uploads the data to ThingSpeak. Additionally, Blynk is used to monitor the data in real-time and receive alerts when the air quality exceeds a certain threshold.

## Setting Up ThingSpeak

1. **Create an Account**: Sign up for a ThingSpeak account at [ThingSpeak](https://thingspeak.com).

2. **Create a Channel**: After logging in, create a new channel to store your air quality data.
    - Go to "Channels" > "My Channels" > "New Channel".
    - Enter a name and description for your channel.
    - Add three fields: Temperature, Humidity, and Air Quality.
    - Save the channel.

3. **Get the Write API Key**: Navigate to the API Keys tab of your channel and copy the "Write API Key".

## Setting Up Blynk

1. **Create an Account**: Download the Blynk app on your smartphone and create an account.

2. **Create a New Project**: 
    - In the Blynk app, create a new project.
    - Select the device as ESP8266 and connection type as WiFi.
    - Copy the Auth Token sent to your email.

3. **Add Widgets**:
    - Add a Value Display widget for Temperature (Virtual Pin V0).
    - Add a Value Display widget for Humidity (Virtual Pin V1).
    - Add a Value Display widget for Air Quality (Virtual Pin V2).
    - Optionally, add a Notification widget for alerts.

## Required Libraries

Install the following libraries through the Arduino Library Manager:
- **Blynk**: For connecting the ESP8266 to the Blynk app.
- **DHT sensor library**: For reading data from the DHT11 sensor.
- **LiquidCrystal_I2C**: For controlling the LCD screen.
- **MQ135**: For reading data from the MQ135 gas sensor.
- **ESP8266WiFi**: For connecting the ESP8266 to WiFi.

## Code Explanation

Here's a brief overview of the code:

1. **Library Inclusions and Definitions**: The necessary libraries are included, and constants are defined for WiFi credentials, ThingSpeak API key, and Blynk authentication token.

2. **WiFi Setup**: The ESP8266 connects to the specified WiFi network.

3. **Sensor Initialization**: The DHT11 and MQ135 sensors are initialized.

4. **Data Reading and Display**:
    - The `sendSensor` function reads data from the sensors and sends it to ThingSpeak and Blynk.
    - The LCD displays the current temperature, humidity, and air quality.

5. **Alerts**:
    - If the air quality exceeds a specified threshold, an LED and buzzer are activated.
    - A Blynk email notification is sent to alert the user.

## How to Run the Project

1. **Open the Arduino IDE** and load the `air_quality_monitoring.ino` file.

2. **Update Credentials**:
    - Replace the placeholders with your Blynk Auth Token, ThingSpeak Write API Key, and WiFi credentials in the code.
3. **Upload the Code** to your ESP8266 board.

4. **Monitor the Output**:
    - Open the Serial Monitor in the Arduino IDE to check the connection status and data logs.
    - Use the Blynk app to monitor real-time data and receive alerts.

## Conclusion

This project provides a comprehensive solution for monitoring air quality in real-time using an ESP8266, with data visualization and alerts through ThingSpeak and Blynk. Follow the steps outlined above to set up and run the project successfully.
-
