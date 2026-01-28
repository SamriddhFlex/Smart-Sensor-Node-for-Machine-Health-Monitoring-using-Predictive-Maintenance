
# Smart Sensor Node for Machine Health Monitoring using Predictive Maintenance

# 2. Project Overview

This project focuses on designing and implementing an IoT-based predictive maintenance system to monitor the health of a machine in real time. A table fan motor is used as the target machine (load).

Multiple sensors are interfaced with STM32 to continuously monitor current consumption, vibration, and temperature, which are key indicators of machine health. The collected data is processed, normalized, and analyzed using an unsupervised machine learning clustering approach to detect normal and anomalous operating conditions.

An ESP32 module is used for communication and cloud connectivity. Sensor data and machine health status are sent to AWS Cloud, where services like S3, DynamoDB, IoT Core, Lambda, and CloudWatch are used for storage, monitoring, and alert generation. The system provides early fault detection, enabling predictive maintenance rather than reactive maintenance.

# 3. Hardware Used

STM32 Microcontroller – Primary controller for sensor data acquisition and processing

ESP32 Microcontroller – Communication and cloud connectivity

ACS712 Current Sensor – Measures motor current consumption

ADXL345 Vibration Sensor – Detects vibration patterns of the motor

Table Fan – Used as the machine/load for health monitoring

OLED Display – Displays real-time sensor values and machine status

UART Communication – Data transfer between STM32 and ESP32

Perf Board (Zero Board) – Hardware mounting and connections

Male and Female Headers – Sensor and module interconnections

DC Jack – Power input

MB102 Power Distribution Board – Power supply management

Voltage Dividers (3.3V) – Voltage level matching

Capacitors – Noise filtering and voltage stabilization

Heat Sink – Thermal management for components

# 4. Hardware Configuration

Sensors (ACS712 and ADXL345) are interfaced with STM32 using appropriate analog and digital interfaces.

OLED display is connected to STM32 for real-time visualization of sensor readings and machine status.

UART communication is established between STM32 and ESP32 for data transfer.

ESP32 handles Wi-Fi communication and cloud data transmission.

Power is distributed using the MB102 power board, with voltage dividers ensuring proper 3.3V logic levels.

All components are mounted on a perf board using headers for stable and modular connections.

# 5. Software Used

STM32CubeIDE – Firmware development and programming for STM32

STM32CubeMX (AI Model Integration) – Peripheral configuration and AI model support

Arduino IDE – Programming and communication handling for ESP32

AWS Cloud Services:

AWS S3 – Storage of sensor datasets and CSV files

AWS IoT Core – Secure device-to-cloud communication

AWS DynamoDB – Structured storage of processed data

AWS Lambda – Serverless data processing

AWS CloudWatch – Threshold monitoring and alert triggering

# 6. Key Components and Process Highlights

Data Acquisition

STM32 continuously collects current and vibration data from the motor.

Data Normalization

Raw sensor values are normalized to improve machine learning performance.

Machine Learning Clustering

An unsupervised clustering-based model is used to learn normal machine behavior.

A reconstruction error is calculated and compared with a predefined threshold.

Health Classification

If error ≤ threshold → Normal condition

If error > threshold → Anomaly detected

Edge-to-Cloud Communication

Machine health data is sent from STM32 to ESP32 via UART.

ESP32 uploads data to AWS Cloud and updates OLED display.

Cloud Monitoring & Alerts

CloudWatch monitors anomaly frequency within a time window.

If the threshold is exceeded, email alerts and dashboard updates are triggered.

# 7. Achievements

Successfully designed a complete end-to-end predictive maintenance system.

Collected and processed 10,000+ real-time sensor data samples.

Implemented unsupervised machine learning for anomaly detection without labeled fault data.

Integrated embedded systems with AWS cloud services for real-time monitoring and alerts.

Demonstrated a scalable and industry-relevant solution applicable to motors, pumps, and industrial machines.
