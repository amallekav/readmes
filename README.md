# Lab 2 – LED Control using ADC, PWM, Timers, and Interrupts

### Course: ECE 40862 – Software for Embedded Systems  
### Fall 2024  
### Instructor: Prof. Lu Su  
### Due: October 4, 2024, by 11:59 PM

---

## Description:
This lab implements an embedded system using the ESP32 Feather V2 board to control an external LED's blinking speed and brightness using a potentiometer and a push button. The following peripherals are used: 
- **PWM** to control the LED’s blinking frequency and brightness (duty cycle).
- **ADC** to read analog input from the potentiometer.
- **RTC (Real-Time Clock)** to display the current time.
- **Timers and Interrupts** to handle periodic tasks and button presses.

### Functionality:
1. **RTC Setup**: The program prompts the user to input the current date and time and sets the RTC.
2. **Time Display**: The current date and time are printed every 30 seconds using a timer interrupt.
3. **Potentiometer Control**:
   - The potentiometer reads values every 100ms and adjusts the LED based on the mode.
   - **Mode 1**: Controls the LED's **blinking frequency** (potentiometer adjusts how fast the LED blinks).
   - **Mode 0**: Controls the LED’s **brightness** (potentiometer adjusts the intensity of the LED).
4. **Button Press**:
   - A press of the button toggles between controlling the LED’s frequency and duty cycle using a button interrupt with debouncing.
   
---

## Hardware Setup:
1. **LED**:
   - **Anode (long leg)** connected to **GPIO 15** (PWM output).
   - **Cathode (short leg)** connected to **GND** through a **220Ω resistor**.
  
2. **Potentiometer**:
   - **Middle pin (wiper)** connected to **GPIO 32 (ADC1)**.
   - **One side pin** connected to **3.3V**.
   - **Other side pin** connected to **GND**.

3. **Button**:
   - On-board button connected to **GPIO 38** (input) with a pull-up resistor.

---

## Software Design:
### Key Components:
- **RTC Initialization**: The user inputs the date and time, which is used to initialize the RTC.
- **Timers**:
  - A timer triggers every **30 seconds** to print the current date and time.
  - A timer triggers every **100ms** to read the potentiometer.
- **PWM Control**:
  - In **Mode 1 (Frequency Control)**, the potentiometer adjusts the LED's blinking speed.
  - In **Mode 0 (Duty Cycle Control)**, the potentiometer adjusts the LED's brightness.
- **Button Handling**:
  - The button toggles between controlling the frequency and duty cycle, and debouncing is implemented to avoid multiple registrations of a single press.

### Code Structure:
- `set_time()`: Initializes the RTC based on user input.
- `display_time()`: Displays the current time every 30 seconds using a timer.
- `read_potentiometer()`: Reads the potentiometer every 100ms and adjusts the LED’s frequency or duty cycle based on the mode.
- `switch_control()`: Handles mode switching (frequency or duty cycle) when the button is pressed.
- `debounce()` and `button_pressed()`: Implements debouncing for the button to avoid multiple triggers.

---

## Submission:
1. **Code File**: Upload your code as `username_lab2.py`.
2. **README File**: This document should be named `username_lab2_README.txt`.
3. **Video Demonstration**:
   - Record a short video demonstrating your hardware setup and the working solution.
   - Briefly explain the connections and functionality before demonstrating the program.
   - Upload the video to YouTube or a similar platform and provide the link below.

### Video Link:
[https://youtu.be/dfM6wAYJ_rQ]

---

## References:
1. [MicroPython Callbacks & Interrupts Documentation](https://docs.micropython.org/en/latest/library/machine.html#machine-callbacks)
2. [ESP32 Feather V2 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-pico-mini-02_datasheet_en.pdf)
3. [Adafruit ESP32 Feather V2 Online Manual](https://learn.adafruit.com/adafruit-esp32-feather-v2)

---
