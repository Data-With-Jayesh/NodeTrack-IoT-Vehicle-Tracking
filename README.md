# 🚗 NodeTrack – IoT Vehicle Tracking System

## 📌 Overview

**NodeTrack** is an IoT-based vehicle tracking system developed using **ESP8266 NodeMCU** and the **NEO-6M GPS Module**.

The system receives real-time GPS data such as **latitude, longitude, date, time, and speed** and displays the information through a web-based interface hosted by the ESP8266.

The current vehicle location can also be opened directly in **Google Maps** using the generated GPS coordinates.

## 🎯 Objectives

* Track vehicle location using GPS.
* Display real-time latitude and longitude.
* Monitor vehicle speed.
* Display GPS date and time.
* Provide a simple web-based monitoring dashboard.
* Open the current location directly in Google Maps.
* Demonstrate IoT-based vehicle tracking using low-cost hardware.

## ✨ Features

* 📍 Real-time latitude and longitude
* 🚗 Vehicle speed monitoring in km/h
* 📅 GPS date display
* ⏰ GPS time display
* 🌐 ESP8266 web server
* 🗺️ Google Maps location link
* 📡 Wi-Fi connectivity
* 💻 Web-based dashboard

## 🛠️ Technologies & Components

### Hardware

* ESP8266 NodeMCU
* NEO-6M GPS Module
* Jumper Wires
* USB Cable / Power Supply

### Software & Libraries

* Arduino IDE
* C/C++
* TinyGPS++ Library
* SoftwareSerial Library
* ESP8266WiFi Library
* HTML
* CSS
* Google Maps

## 🔌 GPS Connection

The project uses `SoftwareSerial` to communicate between the ESP8266 and NEO-6M GPS module.

| NEO-6M GPS | ESP8266                |
| ---------- | ---------------------- |
| TX         | GPIO 4                 |
| RX         | GPIO 5                 |
| VCC        | 3.3V / Suitable supply |
| GND        | GND                    |

> Check your specific NEO-6M module's voltage requirements before connecting it to the ESP8266.

## ⚙️ How the System Works

```text
        NEO-6M GPS
             │
             │ GPS Data
             ▼
      ESP8266 NodeMCU
             │
       GPS Data Processing
             │
       ┌─────┴─────┐
       ▼           ▼
   Wi-Fi Network   GPS Data
       │
       ▼
   ESP8266 Web Server
       │
       ▼
 Web-Based Dashboard
       │
       ▼
 Google Maps Location
```

### Working Process

1. The NEO-6M GPS module receives location information from GPS satellites.
2. The ESP8266 reads GPS data using the TinyGPS++ library.
3. The system extracts:

   * Latitude
   * Longitude
   * Date
   * Time
   * Speed
4. The ESP8266 connects to a Wi-Fi network.
5. An HTTP web server is started on the ESP8266.
6. The GPS information is displayed on a web page.
7. When a valid GPS location is available, a Google Maps link is generated.
8. The user can click the link to view the vehicle location on Google Maps.

## 💻 Web Dashboard

The ESP8266 hosts a simple web page containing a table with:

| Parameter | Description           |
| --------- | --------------------- |
| Latitude  | Current GPS latitude  |
| Longitude | Current GPS longitude |
| Date      | GPS date              |
| Time      | GPS time              |
| Speed     | Current speed in km/h |

## 📚 Libraries Required

Install the following libraries in Arduino IDE:

```text
TinyGPS++
SoftwareSerial
ESP8266WiFi
```

`ESP8266WiFi` is provided with the ESP8266 Arduino core.

## 🚀 Setup Instructions

### 1. Install Arduino IDE

Install Arduino IDE and configure the ESP8266 board package.

### 2. Install Required Libraries

Install the **TinyGPS++** library through the Arduino Library Manager.

### 3. Connect the Hardware

Connect the NEO-6M GPS module to the ESP8266 according to the connection table.

### 4. Configure Wi-Fi

Before uploading the code, update the Wi-Fi credentials:

```cpp
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";
```

**Never upload real Wi-Fi passwords, API keys, or other credentials to a public GitHub repository.**

### 5. Upload the Code

Select the correct ESP8266 NodeMCU board and COM port in Arduino IDE and upload the program.

### 6. Open Serial Monitor

Set the Serial Monitor baud rate to:

```text
9600
```

After connecting to Wi-Fi, the ESP8266 prints its local IP address.

Example:

```text
WiFi connected
Server started
192.168.x.x
```

### 7. Open the Dashboard

Enter the displayed ESP8266 IP address into a browser connected to the same Wi-Fi network.

Example:

```text
http://192.168.x.x
```

The vehicle tracking dashboard will be displayed.

## 🗺️ Google Maps Integration

When valid GPS coordinates are available, NodeTrack generates a Google Maps link using the current latitude and longitude.

The user can click **"Click here"** on the dashboard to open the location in Google Maps.

## 📷 Project Screenshots

Add screenshots of:

* Hardware setup
* NEO-6M GPS module
* ESP8266 NodeMCU
* Serial Monitor
* Web dashboard
* Google Maps location

Example:

```markdown
![NodeTrack Dashboard](images/dashboard.png)
```

## 🔐 Security Note

This project uses Wi-Fi credentials to connect the ESP8266 to a network.

**Do not commit real credentials to GitHub.**

Use placeholders such as:

```cpp
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";
```

## 🚀 Future Scope

* 📱 Android/iOS mobile application
* ☁️ Cloud database integration
* 🗺️ Real-time route tracking
* 📊 Trip history and analytics
* 🚨 Geofencing and alerts
* 🔔 SMS/Email notifications
* 👥 Multiple vehicle tracking
* 🔐 User authentication
* 📡 Long-range communication
* 📈 Advanced tracking dashboard

## 🎓 Project Information

**Project:** NodeTrack – IoT Vehicle Tracking System

**Domain:** Internet of Things (IoT)

**Type:** Engineering Mini Project

**Hardware:** ESP8266 NodeMCU + NEO-6M GPS

## 👨‍💻 Developer

**Jayesh Chaudhari**

Engineering Student | IoT | AI/ML | Web Development

---

⭐ If you find this project useful, consider giving this repository a star!
