##💡 Course Project: Smart Street Light System
##Topic: An Application to Control Smart Lights
Group 5: Octopuses 🐙

1. Project Overview
We aim to build a smart street ✌️ lighting system with the following features:

Lights turn on at a moderate level by default to save electricity ⚡️

Brightness increases 🌟 when a vehicle is detected or during rain

Collects contextual data like temperature and humidity and uploads it to the cloud ☁️

Light poles 🚏 communicate wirelessly

Utilizes solar energy 🌱 during the day to reduce consumption

2. Circuit Diagram
2.1 Master Circuit
Controller: Arduino UNO (for reading multiple analog sensors: light, rain, humidity, temperature)

Communication: UNO sends data to ESP8266 via custom TX-RX (D5, D6) in JSON format

Logic: ESP8266 processes sensor data and motion detection signals to control lighting

Data Upload: Sends sensor data to MQTT broker using the MQTT protocol

2.2 Child Circuit
Subscribes to MQTT topics from the Master

Uses motion sensor input to control light brightness

Child nodes only receive data; they do not send

3. System Architecture
We use the MQTT protocol for communication between devices and from device to server.
Broker: HiveMQ
