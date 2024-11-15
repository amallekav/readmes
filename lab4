ESP32 Web Server for IoT Control and Monitoring
This project creates a web server on the ESP32 microcontroller that allows you to monitor temperature and hall sensor readings, as well as control an LED through a web interface. The ESP32 connects to Wi-Fi and serves a webpage accessible from any device on the same network.

Requirements
Hardware:
ESP32 microcontroller
Onboard red LED connected to GPIO pin 13 

Software:
MicroPython or compatible ESP32 development environment
Wi-Fi network access
Project Files
espserver.py: This is the main program file that:
Connects the ESP32 to Wi-Fi.
Serves a webpage displaying sensor data (temperature and hall sensor readings) and the current LED state.
Allows users to control the LED state via buttons on the webpage.
How It Works
Wi-Fi Connection: The ESP32 connects to Wi-Fi using the specified SSID and password.

Web Server Setup:

The ESP32 acts as an HTTP server, listening for connections on port 80.
It generates an HTML webpage (using the web_page() function) that displays temperature and hall sensor values and includes buttons to turn the LED on or off.
Handling Client Requests:

When a client (browser) connects to the ESP32’s IP address, the ESP32 reads the incoming request.
Based on the request:
If the user clicks “RED ON,” the ESP32 turns the LED on.
If the user clicks “RED OFF,” the ESP32 turns the LED off.
The webpage automatically updates to reflect the LED’s current state and the latest sensor values.
Sensor Monitoring:

Each time the webpage is accessed, it displays updated values for temperature and hall sensor readings.
These values are read directly from the ESP32’s onboard sensors.
Setup Instructions
Update Wi-Fi Credentials:

Modify the ssid and password variables in the code to match your Wi-Fi network credentials.
Upload and Run the Code:

Upload the espserver.py file to the ESP32 and execute it.
Access the Webpage:

Once the ESP32 is connected to Wi-Fi, it will print its IP address to the terminal.
Open a web browser on any device connected to the same Wi-Fi network and enter the IP address to access the webpage.

Expected Results
The webpage should display:
Temperature and hall sensor readings, updated each time you refresh the page.
The current state of the red LED.
Buttons to turn the red LED ON and OFF.
When you click the "RED ON" or "RED OFF" buttons:
The LED on the ESP32 should respond immediately.
The LED state on the webpage should reflect the current state.
Troubleshooting
No Wi-Fi Connection:
Ensure the SSID and password are correct.
Confirm that the ESP32 is within range of the Wi-Fi network.
Webpage Not Loading:
Ensure you’re on the same Wi-Fi network as the ESP32.
Confirm you’re entering the correct IP address (shown in the ESP32’s terminal output).
Demo Video

https://youtu.be/P36z-UYtNzY 
