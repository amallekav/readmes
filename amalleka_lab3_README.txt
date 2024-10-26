**Lab 3 – WiFi Connectivity, NTP Synchronization, and Sleep Modes**  
**Course:** ECE 40862 – Software for Embedded Systems  
**Fall 2024**  
**Instructor:** Prof. Lu Su  
**Due:** October 24, 2024, by 11:59 PM  

### Description:
This lab implements an embedded system using the ESP32 Feather V2 board to establish WiFi connectivity, synchronize with an NTP server, manage LED control via touch sensor inputs, and use sleep modes for power efficiency. The program includes functionalities such as time synchronization with an NTP server, periodic display of the current time, and the ability to wake up from deep sleep using external events.

### Functionality:
1. **WiFi Setup**:
   - The ESP32 connects to a WiFi network using the provided SSID and password. 
   - If the connection fails after 10 retries, the ESP32 will reset itself.

2. **NTP Time Synchronization**:
   - The RTC (Real-Time Clock) is synchronized with an NTP server (`pool.ntp.org`), and the local time is adjusted by the specified timezone offset (in this case, UTC-4).

3. **Timers and Interrupts**:
   - **Timer 1**: Displays the current date and time every 15 seconds.
   - **Timer 2**: Reads touch sensor input every 50 milliseconds, adjusting the color of a NeoPixel LED based on the input state.
   - **Timer 3**: Puts the ESP32 into deep sleep after 30 seconds.

4. **Wake-Up Handling**:
   - The ESP32 wakes up from deep sleep either through a timer interrupt or via external input (EXT0 wake-up), triggered by the wake button.

5. **Touch Input**:
   - The touch sensor reads values every 50 milliseconds. If the input crosses a predefined threshold, the NeoPixel LED color changes to green. If not, the LED is turned off.

### Hardware Setup:
- **Red LED**:
  - **Pin 13** – connected to an external red LED (used to indicate power and wake-up events).
  
- **NeoPixel LED**:
  - **Pin 0** – connected to a NeoPixel LED (used to display color based on touch sensor input).
  - **Pin 2 (Output Mode)** – controls power to the NeoPixel LED.
  
- **Touch Sensor**:
  - **Pin 4** – connected to a touch sensor for input.

- **Wake Button**:
  - **Pin 33** – connected to an external button, configured to wake up the ESP32 from deep sleep.

- **WiFi Configuration**:
  - **SSID**: ankitha
  - **Password**: ankithapass

### Software Design:
- **WiFi Connection**: Connects to WiFi using `connect_wifi()`.
- **Time Synchronization**: Synchronizes time via NTP using `sync_time()`.
- **Display Time**: Prints the current date and time every 15 seconds with `display_datetime()`.
- **Touch Sensor Calibration**: Calibrates touch input to set a threshold using `calibrate_touch()`.
- **Touch Sensor Handling**: Reads touch input every 50 ms, changing the NeoPixel LED color accordingly.
- **Sleep Mode**: Puts the device into deep sleep after 30 seconds using `go_to_sleep()`.
- **Wake-Up Handling**: Detects if the wake-up is due to an external pin (button) or a timer.

### Code Structure:
- **main()**: Handles the overall flow, including WiFi connection, time synchronization, touch calibration, and setting up timers for periodic tasks.
- **check_touch()**: Reads the touch sensor and adjusts the NeoPixel LED color based on the input value.
- **calibrate_touch()**: Sets the threshold for touch detection.
- **display_datetime()**: Displays the current time.
- **go_to_sleep()**: Puts the ESP32 into deep sleep for 1 minute.
- **connect_wifi()**: Connects to the WiFi network and retries if necessary.
- **sync_time()**: Synchronizes the RTC with the NTP server.

### Submission:
**Code File:**  
Upload your code as **x-amallekav_lab3.py**.

**README File:**  
This document should be named **x-amallekav_lab3_README.txt**.

### Video Demonstration:
Record a short video demonstrating your hardware setup and the working solution. Briefly explain the connections and functionality before demonstrating the program.  
**Video Link:**  
[https://youtu.be/TeALeh0svnA]

### References:
- MicroPython Documentation on Timers, Sleep Modes, and Interrupts
- ESP32 Feather V2 Datasheet
- NeoPixel LED Documentation
