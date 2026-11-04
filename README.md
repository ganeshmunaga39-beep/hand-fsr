🖐️ Smart Hand Pressure Monitoring System
ESP32 | Force Sensitive Resistors | MPU6050 | Firebase | IoT Dashboard

<p align="center">
<img src="https://img.shields.io/badge/Platform-ESP32-blue?style=for-the-badge&logo=espressif" />
<img src="https://img.shields.io/badge/IoT-Firebase-orange?style=for-the-badge&logo=firebase" />
<img src="https://img.shields.io/badge/Frontend-HTML%20%7C%20CSS%20%7C%20JavaScript-yellow?style=for-the-badge" />
<img src="https://img.shields.io/badge/Sensors-FSR%20%2B%20MPU6050-green?style=for-the-badge" />
</p>

🌐 Live Project

Live Dashboard: https://ganeshmunaga39-beep.github.io/hand-fsr/

GitHub Repository: https://github.com/ganeshmunaga39-beep/hand-fsr

📌 1. Project Overview

The Smart Hand Pressure Monitoring System is an IoT-based monitoring project designed to measure hand pressure, movement, acceleration, and impact using multiple sensors connected to an ESP32 microcontroller.

The system uses five Force Sensitive Resistors (FSRs) to detect pressure applied at different positions of the hand. An MPU6050 sensor measures acceleration and angular velocity, helping monitor hand movement and sudden impacts.

The ESP32 collects sensor readings and sends the information to Firebase Realtime Database. A web-based dashboard retrieves the information from Firebase and displays it in real time.

The dashboard provides visual monitoring through live sensor values, statistical summaries, graphical trends, and alert indicators.

The main objective is to develop a smart, connected monitoring system that can help observe hand pressure distribution and movement patterns.

🎯 2. Project Objectives
Measure pressure applied at multiple positions of the hand.
Monitor pressure variations using five FSR sensors.
Measure hand movement using an MPU6050 accelerometer and gyroscope.
Detect unusually high pressure and sudden impacts.
Transmit sensor data wirelessly using ESP32 and Wi-Fi.
Store and retrieve sensor information using Firebase Realtime Database.
Display live sensor readings through a web dashboard.
Visualize sensor data using interactive graphs.
Monitor ESP32 device status and connectivity.
⚙️ 3. Hardware Components
Component	Quantity	Purpose
ESP32 Development Board	1	Main microcontroller and Wi-Fi communication
Force Sensitive Resistor (FSR)	5	Measures applied pressure
MPU6050 Sensor	1	Measures acceleration and angular velocity
Connecting Wires	As required	Hardware connections
Breadboard / PCB	1	Circuit assembly
Power Supply	1	Powers the electronic system
3.1 ESP32 Microcontroller

The ESP32 is the main processing unit of the project.

Its responsibilities include:

Reading analog values from five FSR sensors.
Communicating with the MPU6050 sensor.
Processing sensor readings.
Detecting pressure and impact conditions.
Connecting to Wi-Fi.
Uploading sensor data to Firebase Realtime Database.
3.2 Force Sensitive Resistors (FSR)

Five FSR sensors are used to measure pressure at different hand positions.

Each sensor changes its electrical resistance depending on the applied force.

The system monitors:

FSR1 – Pressure Sensor 1.
FSR2 – Pressure Sensor 2.
FSR3 – Pressure Sensor 3.
FSR4 – Pressure Sensor 4.
FSR5 – Pressure Sensor 5.

These readings help identify which sensor position experiences the highest pressure.

Pressure-related calculations:

Total Pressure Reading: Sum of all five sensor readings.
Average Pressure Reading: Average of the five sensor readings.
Maximum Pressure Reading: Highest reading among the five sensors.
Maximum Sensor: Identifies the sensor currently recording the highest value.

Note: FSR readings are sensor output values. They should not be interpreted directly as force in Newtons unless the sensors have been calibrated.

3.3 MPU6050 Sensor

The MPU6050 is a 6-axis motion tracking sensor containing:

3-axis accelerometer.
3-axis gyroscope.
Temperature sensor.

The accelerometer measures movement along three axes:

Acceleration X
Acceleration Y
Acceleration Z

The gyroscope measures angular velocity:

Gyroscope X
Gyroscope Y
Gyroscope Z

The sensor also provides temperature and total acceleration information.

These measurements help monitor hand movement, orientation changes, and sudden motion.

🖥️ 4. Software Technologies
Technology	Application
HTML5	Dashboard structure
CSS3	Dashboard styling and responsive layout
JavaScript	Live data processing and interface updates
Firebase Realtime Database	Cloud data storage and synchronization
Firebase Authentication	Anonymous authentication
Chart.js	Real-time graphical visualization
ESP32 Firmware	Sensor acquisition and IoT communication
GitHub Pages	Website hosting
🏗️ 5. System Architecture

The project works through the following data flow:

text
       HAND PRESSURE / MOVEMENT
                  |
                  v
        +-------------------+
        |   5 FSR Sensors   |
        |  Pressure Values  |
        +-------------------+
                  |
                  |
        +-------------------+
        |     MPU6050       |
        | Accelerometer     |
        | Gyroscope         |
        +-------------------+
                  |
                  v
        +-------------------+
        |       ESP32       |
        | Data Acquisition  |
        | Data Processing   |
        +-------------------+
                  |
                  | Wi-Fi
                  v
        +-------------------+
        | Firebase Realtime |
        |     Database      |
        |                   |
        | /latest           |
        | /history          |
        +-------------------+
                  |
                  | Internet
                  v
        +-------------------+
        |  Web Dashboard    |
        | HTML CSS JS       |
        +-------------------+
                  |
          +-------+-------+
          |       |       |
          v       v       v
       Live    Graphs   Alerts
       Values  Trends   Status

🔄 6. Working Principle
Step 1: Sensor Data Collection

The five FSR sensors continuously measure pressure applied at different positions of the hand.

The MPU6050 simultaneously measures acceleration and angular velocity.

Step 2: ESP32 Processing

The ESP32 reads the sensor values and processes the information.

It calculates relevant pressure statistics and monitors movement and impact conditions.

Step 3: Wi-Fi Communication

The ESP32 connects to a Wi-Fi network and communicates with Firebase.

Sensor readings are uploaded periodically. The dashboard describes the upload interval as approximately every 2 seconds.

Step 4: Firebase Data Storage

Firebase Realtime Database acts as the cloud-based data storage and synchronization platform.

The project uses two main database paths:

/latest – Stores the latest sensor readings and device information.
/history – Stores historical sensor readings for monitoring trends.
Step 5: Web Dashboard

The website retrieves the latest information from Firebase and updates the dashboard automatically.

JavaScript processes the incoming values and displays them using sensor cards, status indicators, and charts.

Step 6: Alert Monitoring

The dashboard displays pressure and impact alerts based on configured thresholds.

This allows users to identify potentially unusual sensor readings.

📊 7. Dashboard Features
7.1 Live FSR Monitoring

The dashboard displays all five FSR sensor readings.

Each sensor has an individual pressure indicator and threshold reference.

Default displayed threshold: 2500.

7.2 Pressure Statistics

The dashboard calculates and displays:

Total pressure reading.
Average pressure reading.
Maximum pressure reading.
Sensor with maximum pressure.
Date and time information.

These statistics help understand pressure distribution across the five sensor positions.

7.3 MPU6050 Monitoring

The motion monitoring section displays:

Parameter	Description
Accel X	Acceleration along X-axis
Accel Y	Acceleration along Y-axis
Accel Z	Acceleration along Z-axis
Gyro X	Angular velocity around X-axis
Gyro Y	Angular velocity around Y-axis
Gyro Z	Angular velocity around Z-axis
MPU Temperature	Sensor temperature
Total Acceleration	Combined acceleration magnitude
7.4 Pressure Alert

The pressure alert system monitors FSR sensor readings against the configured threshold.

It helps identify when pressure readings exceed the defined limit.

7.5 Impact Alert

The impact monitoring feature uses MPU6050 acceleration data to identify sudden movement or impact conditions.

Default displayed impact threshold: 20 m/s².

7.6 Live Graph Visualization

The dashboard includes four graphical monitoring sections:

FSR Live Trend: Displays pressure variations across the five sensors.
Acceleration Trend: Displays acceleration changes along X, Y, and Z axes.
Gyroscope Trend: Displays angular velocity variations.
Total Acceleration & Alerts: Displays total acceleration trends alongside alert information.

The graphs use Chart.js for visualization.

Users can select the number of graph points and clear the displayed graph history.

7.7 ESP32 Device Information

The dashboard also displays device-related information:

Board identification.
Wi-Fi signal strength (RSSI).
Device IP address.
Device MAC address.
ESP32 uptime.
Available free heap memory.

This helps monitor the connected hardware device.

7.8 Connection Status

The dashboard displays the Firebase connection state.

It indicates whether the system is connected or disconnected and provides feedback when database reading encounters an error.

☁️ 8. Firebase Integration

Firebase Realtime Database is used for communication between the ESP32 and the web application.

Database URL:

https://hand-fsr-default-rtdb.asia-southeast1.firebasedatabase.app

Database structure:

text
Firebase Realtime Database
|
+-- latest
|    |
|    +-- FSR sensor readings
|    +-- MPU6050 readings
|    +-- Alert information
|    +-- Device information
|
+-- history
     |
     +-- Historical sensor records
     +-- Previous measurements


The exact field names and record structure should match the ESP32 firmware.

Firebase Features Used
Realtime Database.
Firebase JavaScript SDK.
Realtime value listeners.
Anonymous authentication.
Connection-state monitoring.

Anonymous authentication is used by the web application to authenticate users without requiring a traditional login form.

Security Note: Firebase API keys used in browser applications are not secret credentials. Configure Firebase Realtime Database security rules and authentication permissions carefully. Never allow unrestricted public database writes.

📈 9. Applications

This project can be useful as a prototype for:

Hand pressure monitoring.
Smart wearable sensor systems.
Hand movement observation.
Rehabilitation research prototypes.
Human-machine interaction experiments.
IoT-based sensor monitoring.
Pressure distribution analysis.
Educational embedded systems projects.

The system is an experimental monitoring prototype and is not a certified medical or diagnostic device.

🚀 10. How to Access the Project

You can access the live dashboard directly through your browser.

Live Website:

https://ganeshmunaga39-beep.github.io/hand-fsr/

No software installation is required to view the hosted dashboard.

💻 11. Run the Project Locally
Requirements
Git
A web browser
Internet connection
Step 1: Clone the repository
bash
git clone https://github.com/ganeshmunaga39-beep/hand-fsr.git

Step 2: Open the project directory
bash
cd hand-fsr

Step 3: Run the website

Open index.html in your browser.

Alternatively, use the VS Code Live Server extension.

Step 4: Configure Firebase

Ensure that the Firebase configuration points to your own Firebase project if you are creating a separate deployment.

Enable the required Firebase Authentication provider and configure the Realtime Database security rules.

Step 5: Connect the ESP32

For live hardware readings, connect and configure the ESP32 firmware to:

Read the five FSR sensors.
Read MPU6050 measurements.
Connect to Wi-Fi.
Publish the expected data structure to Firebase.
Update /latest and, where configured, /history.

Important: The current GitHub repository contains the web dashboard (index.html). The ESP32 firmware and physical hardware wiring instructions should be added separately if you want the complete hardware project to be reproducible.

📁 12. Project Structure
text
hand-fsr/
|
+-- index.html
|    |
|    +-- HTML Dashboard
|    +-- CSS Styling
|    +-- JavaScript Logic
|    +-- Firebase Integration
|    +-- Chart.js Visualization
|
+-- README.md
     |
     +-- Project Documentation

🔮 13. Future Improvements

The project can be improved with the following additional features:

Add historical data analysis and downloadable CSV reports.
Implement user login and role-based access.
Add configurable pressure thresholds.
Include individual sensor calibration.
Improve graphical pressure distribution visualization.
Add mobile notifications for high-pressure events.
Develop a mobile application.
Add long-term sensor data analysis.
Implement improved motion and impact classification.
Design a wearable enclosure for the sensor system.
Add data export and reporting functionality.
⚠️ 14. Limitations
FSR sensor readings depend on sensor calibration and physical placement.
Pressure readings are raw or relative sensor values unless calibrated.
Sensor readings depend on Wi-Fi and Firebase connectivity.
Impact detection depends on the configured threshold and sensor orientation.
Accurate physical force measurement requires appropriate calibration.
The project is intended for experimental monitoring and not safety-critical applications.
👨‍💻 15. Developer

Developed by: Ganesh Munaga

Project Name: Smart Hand Pressure Monitoring System

Domain: Internet of Things (IoT), Embedded Systems, Sensor Monitoring, and Web Development.

GitHub: https://github.com/ganeshmunaga39-beep

📜 16. License

This project is available for educational and research purposes.

If you plan to distribute or reuse this project, add an appropriate open-source license to the repository.

<p align="center">
<b>🖐️ Smart Hand Pressure Monitoring System</b>
<br/>
<i>Connecting Hand Pressure, Motion Sensing, and IoT Technology.</i>
</p>
