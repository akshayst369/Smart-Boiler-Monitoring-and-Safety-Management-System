# Smart Boiler Monitoring and Safety Management System

An IoT-based system that monitors industrial boiler parameters in real time and provides safety status through a web dashboard using MQTT communication.

---

## 📌 Project Overview

Industrial boilers operate under high temperature and pressure, making continuous monitoring essential for safety and efficiency.  
This project implements a **Smart Boiler Monitoring and Safety Management System** using an ESP32 microcontroller, secure MQTT communication, and a web-based dashboard.

The system continuously collects:

- Temperature
- Pressure
- Flow rate  

and classifies the boiler state as:

- **NORMAL**
- **WARNING**
- **DANGER**

based on predefined safety thresholds.

---

## 🛠️ System Architecture

ESP32 ---> HiveMQ Cloud (MQTT) ---> Web Dashboard

1. ESP32 reads sensor data (or simulated values).
2. Data is published securely using MQTT over TLS.
3. Web dashboard subscribes and visualizes live data.
4. Safety logic evaluates and displays system status.

---

## ⚙️ Technologies Used

### Hardware

- ESP32 Dev Board  
- Temperature Sensor (DS18B20 or equivalent)  
- Pressure Sensor  
- Flow Sensor  

### Software & Tools

- Arduino IDE  
- MQTT (HiveMQ Cloud)  
- HTML, CSS, JavaScript  
- PubSubClient Library  
- WiFiClientSecure  

---

## 📡 MQTT Topic Structure

boiler/{state}/{district}/{company}/{boiler_id}/data
Example:
boiler/Maharashtra/Pune/CompanyA/Boiler01/data

---

## 📊 Web Dashboard Features

- Real-time temperature display  
- Real-time pressure display  
- Real-time flow rate  
- Location hierarchy (State > District > Company > Boiler ID)  
- Automatic safety status detection  
- Device offline detection  

---

## 🚨 Safety Logic

| Condition | Status |
|----------|--------|
| Temp ≤ 200°C and Pressure ≤ 6 bar | NORMAL |
| Temp > 200°C or Pressure > 6 bar | WARNING |
| Temp > 220°C or Pressure > 8 bar | DANGER |

---

## 🔐 Security

- Secure MQTT over TLS (port 8883 / 8884)
- Username & password authentication
- Root CA certificate validation

---

## 📁 Project Structure

---

## 🚀 How to Run

### ESP32

1. Open `arduinoesp32.ino` in Arduino IDE  
2. Set WiFi credentials  
3. Set HiveMQ credentials  
4. Upload to ESP32  

### Dashboard

1. Open `dashboard.html` in browser  
2. Ensure internet connection  
3. Data appears automatically  

---

## 📈 Future Enhancements

- Mobile app version  
- Historical data storage (Firebase / InfluxDB)  
- Graph visualization  
- SMS / Email alerts  
- AI-based fault prediction  

---

## 👨‍💻 Author

Akshay  
Electronics and Communication Engineering  
IoT & Embedded Systems Project  

---

## 📜 License

This project is for academic and educational purposes.  
Free to use and extend.
