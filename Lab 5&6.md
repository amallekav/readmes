# **Motion Detection System**

## **Overview**
This project implements a motion detection system using an **ESP32 microcontroller** and an **MPU6050 accelerometer**. 
The system detects motion, connects to Wi-Fi, and sends notifications via **IFTTT webhook**. 
It also monitors states using **ThingSpeak** and provides visual feedback with **NeoPixel** and **red LEDs**.

---

## **Features**
- Motion detection with MPU6050.
- Wi-Fi connectivity for remote notifications.
- Visual feedback using LEDs.
- Integration with IFTTT and ThingSpeak.

---

## **Hardware Requirements**
- ESP32 microcontroller
- MPU6050 accelerometer and gyroscope
- NeoPixel LED (1 pixel)
- Red LED
- Connecting wires and breadboard

---

## **Software Requirements**
- MicroPython firmware installed on ESP32
- `urequests` library for HTTP requests

---

## **Setup**
1. Connect the MPU6050 to the ESP32 using I2C pins:
   - **SCL**: GPIO 14
   - **SDA**: GPIO 22
2. Connect the NeoPixel LED to **GPIO 0** and the red LED to **GPIO 13**.
3. Update Wi-Fi credentials and API URLs in the code.
4. Flash the code to the ESP32 using Thonny.

---

## **Video Demo**
(https://youtu.be/dBOpbpwvB3o)

---
