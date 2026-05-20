# 🏠 Smart Room Automation System

A complete embedded systems project integrating real-time control, IoT communication, security, and automation using STM32 and ESP8266.

---

## 📸 System Overview

https://github.com/user-attachments/assets/1.jpeg

---

## 🚀 Features

### 🔐 Security System
- Password authentication from mobile app
- Door control using servo motor
- Alarm after incorrect attempts

### 💡 Smart Lighting
- Manual ON/OFF
- Automatic mode (PIR-based)

### 🌡️ Environment Monitoring
- Temperature & humidity (DHT22)

### 🌬️ Fan Control
- PWM control
- Proportional control

### 📡 Wireless Communication
- WiFi via ESP8266
- HTTP API

---

## 🧠 Architecture

```
PHONE APP
    ↓ WiFi
ESP8266MOD
    ↓ UART
STM32
    ↓
Sensors + Actuators
```

---

## 🔧 Hardware

- STM32 F446RE
- ESP8266MOD
- PIR Sensor
- DHT22
- Servo SG90
- 5V Fan
- LEDs
- Buzzer
- MB102 Power Supply

---

## ⚡ Power Notes

- ESP8266 → ONLY 3.3V
- Servo/Fan → external 5V
- Common GND required

---

## 🔌 Pin Map

| Function | Pin |
|----------|-----|
| UART TX | PA2 |
| UART RX | PA3 |
| Servo | PA8 |
| Fan | PB6 |
| PIR | PC0 |
| DHT22 | PC1 |
| LEDs | PB0–PB13 |
| Buzzer | PB10 |

---

## 📦 Software

Modules:
- UART
- Sensors
- Control
- Actuators
- Status

Main loop:

```c
while(1)
{
    UART_Process();
    Sensors_Update();
    Control_Update();
    Actuators_Update();
    Status_Update();
}
```

---

## 📡 Protocol

Commands:

```
PASS:1234
LIGHT_MODE:AUTO
LIGHT:ON
SET_TEMP:25
STATUS?
```

Response:

```
STATUS:DOOR=OPEN;TEMP=27;FAN=60
```

---

assets/2.jpg
assets/2.jpg


## 🚀 Conclusion

A complete IoT embedded system demonstrating real-world engineering concepts.
