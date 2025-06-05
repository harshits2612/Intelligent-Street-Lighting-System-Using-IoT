
🌟 Smart Street Light System
An Application to Control Smart Lights


📘 Table of Contents
Project Overview

Features

Circuit Diagrams

Master Circuit

Child Circuit

System Architecture

Installation

Usage

Files in the Project

Dependencies

Configuration

Troubleshooting

Contributors

License

📖 Project Overview
The Smart Street Light System is an IoT-based solution designed to conserve energy, adapt lighting based on environmental and motion-based triggers, and enable wireless communication between light poles. The system also integrates environmental monitoring and cloud-based data logging.

✨ Features
⚡ Energy Efficiency: Lights turn on with moderate brightness to reduce electricity consumption.

🌧️ Adaptive Lighting: Brightness increases when motion is detected or during rain.

🌡️ Environmental Monitoring: Collects temperature, humidity, and rain data.

📡 Wireless Communication: Uses MQTT for device-to-device and cloud communication.

🌱 Green Energy: Solar-powered to minimize reliance on grid electricity.

🔌 Circuit Diagrams
🧠 Master Circuit
Microcontroller: Arduino UNO (for analog signal management)

Sensors:

LDR (Light Intensity)

Rain Sensor

DHT11/DHT22 (Temperature & Humidity)

Communication: UART TX-RX to ESP8266 NodeMCU

ESP8266 Functions:

Processes sensor & motion data

Controls lighting logic

Publishes data to HiveMQ MQTT Broker

📡 Child Circuit
Microcontroller: ESP8266 NodeMCU

Functions:

Subscribes to Master’s MQTT topic

Detects local motion via PIR sensor

Adjusts brightness accordingly

Operates based on master’s control logic

🏗️ System Architecture
The system uses the MQTT protocol to enable real-time, lightweight communication:

Master Node ➝ Child Nodes: Motion & environmental commands

Master Node ➝ MQTT Broker: Cloud-based logging (HiveMQ)

Cloud Access: Data is accessible for real-time monitoring and future analytics.

![System Architecture Diagram - Insert Diagram Here]

🛠️ Installation
Clone the Repository:

bash
Copy
Edit
git clone (https://github.com/harshits2612/Intelligent-Street-Lighting-System-Using-IoT)
Upload the Firmware:

Uno.ino → Arduino UNO (Master Circuit)

Node.ino → ESP8266 NodeMCU (Master)

Child.ino → ESP8266 NodeMCU (Child Nodes)

Configure Wi-Fi Credentials:

In both Node.ino and Child.ino:

cpp
Copy
Edit
const char* ssid = "Your_WIFI";
const char* password = "Your_WIFI_password";
Run the Streamlit App (Optional UI):

bash
Copy
Edit
streamlit run demo.py
📁 Files in the Project
File	Description
Uno.ino	Arduino UNO code for environmental sensing
Node.ino	Master ESP8266 logic for data processing and MQTT publishing
Child.ino	Child ESP8266 logic for motion-based light control
demo.py	Streamlit-based UI for monitoring and demo

📦 Dependencies
Hardware:

Arduino UNO

ESP8266 NodeMCU x2+

PIR Motion Sensor

LDR, Rain Sensor, DHT11/DHT22

Solar Panels (optional for green energy setup)

Software:

Arduino IDE

Streamlit (pip install streamlit)

MQTT Broker: HiveMQ

⚙️ Configuration
Wi-Fi settings in Node.ino and Child.ino

MQTT topics can be customized in the respective .ino files

Adjust sensor threshold values in code as per your environment

🧪 Troubleshooting
Wi-Fi Not Connecting?

Double-check SSID/password.

Make sure your ESP8266 board is supported by your router (2.4GHz).

Data Not Showing on Streamlit UI?

Ensure MQTT broker is reachable.

Check sensor data JSON formatting.

Child Lights Not Reacting?

Verify MQTT subscriptions.

Ensure PIR sensors are functional.

👨‍💻 Contributors
Developed by: Harshit











