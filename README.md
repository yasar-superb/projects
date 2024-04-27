Accident Detection and Alert System

Introduction:
This project is an Accident Detection and Alert System designed to detect impacts and notify emergency contacts with the GPS location in case of an accident. The system utilizes an Arduino board, a SIM900 GSM module, and an accelerometer sensor to detect sudden impacts. Upon impact detection, the system sends an SMS alert containing the GPS coordinates to predefined emergency contacts.

Components:
Arduino Uno board
SIM900 GSM module
ADXL335 accelerometer sensor
Buzzer
Push button
Jumper wires
Libraries Used:
AltSoftSerial: For serial communication with the SIM900 module.
TinyGPS++: For parsing GPS data.
SoftwareSerial: For serial communication with the accelerometer and debugging.
Wire: For I2C communication.
Hardware Setup:
Connect the accelerometer sensor to the Arduino board.
Connect the SIM900 module to the Arduino board.
Connect the buzzer and push button to the Arduino board.
Ensure proper power supply to all components.
Code Explanation:
Initialization (setup function):
Initialize serial communication with a baud rate of 9600.
Initialize communication with the SIM900 module.
Configure pins for the buzzer and push button.
Initialize variables and set initial states.
Impact Detection (Impact function):
Read accelerometer sensor values and calculate magnitude.
If the magnitude exceeds a predefined threshold, set the update flag to indicate impact detection.
GPS Data Retrieval (getGps function):
Read GPS data using the TinyGPS++ library.
Extract latitude and longitude coordinates.
Sending Alerts (sendAlert and makeCall functions):
sendAlert function sends an SMS alert containing GPS coordinates to predefined emergency contacts.
makeCall function initiates a call to emergency contacts using the SIM900 module.
Parsing Received SMS (parseData function):
Parses incoming SMS messages and executes corresponding actions.
If a specific command is received, such as "get gps", it triggers GPS data retrieval and sends the location to the sender.
Main Loop (loop function):
Continuously checks for impact detection.
If an impact is detected, triggers alert functions and sets a delay for subsequent alerts.
Monitors the push button for manual reset of impact detection.
SendAT function:
Sends AT commands to the SIM900 module and waits for expected responses.
Usage:
Power on the Arduino board and GSM module.
Upload the provided code to the Arduino.
Ensure the SIM card is inserted into the GSM module and has sufficient credit.
The system is now ready to detect impacts and send alerts.
Notes:
Ensure proper calibration of the accelerometer sensor for accurate impact detection.
Test the system thoroughly before deploying it in real-life scenarios.
Check for proper network coverage to ensure reliable SMS and call functionalities.
Troubleshooting:
If the system fails to detect impacts or send alerts, check the hardware connections and SIM card status.
Verify that the GSM module is properly initialized and connected to the network.
Future Improvements:
Implement real-time monitoring and tracking functionalities.
Enhance the system to detect different types of accidents or emergencies.
Integrate additional sensors for more comprehensive monitoring and alerting capabilities.
