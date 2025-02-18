# UniLogic PLC Order Fulfillment System
📌 Author: [Xabier Þór]

📌 License: Apache License 2.0

📌 Version: Beta (UniLogic 1.39.103)

📌 Status: Open Source

📌 Overview

This project is an open-source UniLogic PLC program for QR-based order fulfillment using a robotic system. It allows automation of order pickup, barcode scanning, logging, and delivery tracking in an industrial setting.

📦 Features:

✅ Barcode scanning & order processing (DataLogic Matrix 220)

✅ Real-time order tracking & logging

✅ Robot-controlled order delivery

✅ Web-based interface & HMI for order management

✅ Digital indicator for new orders

✅ Manual override (force-picking button)



📌 Use Case:

This PLC program is designed for automated storage & retrieval, where customers scan QR codes to receive their stored orders.


📌 System Workflow

1️⃣ Customer Side:


Customer scans a QR code with their order number.
Order number appears in the order list on the storage side.

2️⃣ Storage Side:

A light flashes (via digital output) to alert staff of a new order.
Staff places an order with the matching barcode in the pickup location.
The barcode is scanned, and if it matches an order in the list, it triggers the next steps.

3️⃣ Robot & Order Processing:

If there is a valid match, the system sends a command to the robot to pick & place the order in the delivery window.
The order is removed from the list and logged as delivered.

4️⃣ Additional Features:

Force-picking button (manual override).
Other functionalities previously described.

📌 System Architecture

The program consists of modular function blocks:


1️⃣ Barcode Handling (DataLogic Matrix 220)

📌 Function Blocks:


QR_Reader_1: Reads barcode data from scanner 1.

QR_Reader_2: Reads barcode data from scanner 2.

📌 Features:

✅ Converts barcode bits into readable data

✅ Matches QR data with stored order numbers

✅ Triggers actions for order pickup

2️⃣ Data Handling & Logging

📌 Function Blocks:


Delivered_Log: Records orders that have been picked up.

Pickup_Data: Stores waiting orders.

📌 Features:

✅ Stores order information dynamically

✅ Removes orders from the list after pickup

✅ Logs timestamps for each order

3️⃣ Robot Control (DoBot Integration)

📌 Function Blocks:


DoBot_Control: Sends movement commands to the DoBot robotic arm.

📌 Features:

✅ Controls robotic arm for order placement

✅ Syncs robot actions with barcode data

4️⃣ Real-Time Clock (RTC) & Timestamping

📌 Function Blocks:


RTC_Handler: Fetches real-time data.

Timestamp_Generator: Adds timestamps to logs.

📌 Features:

✅ Ensures accurate order tracking

✅ Displays real-time timestamps on HMI

5️⃣ Indicator Light & HMI Display

📌 Function Blocks:


IO_Indicators: Controls LED signals for storage workers.

📌 Features:

✅ Lights up when a new order is added

✅ Visual confirmation for order processing

📌 Setup Instructions

🔹 Requirements

Hardware:

Unitronics UniStream PLC

DoBot robotic arm

DataLogic Matrix 220 Barcode Scanners

Software:

UniLogic 1.39.103

🔹 Installation

1️⃣ Open UniLogic and load PLC_OrderSystem.ulpr

2️⃣ Connect the PLC to the barcode scanners & DoBot

3️⃣ Adjust IP settings for the web-based HMI

4️⃣ Deploy the program to the UniStream PLC

5️⃣ Test the QR scanning, order logging, and robot movement


📌 Web Interface & HMI

🖥️ The system includes a built-in web server & HMI to allow:


Viewing pending orders

Monitoring logs & timestamps

Controlling manual order processing

📌 License & Disclaimer

📌 License:

This project is licensed under the Apache License 2.0, allowing free use, modification, and distribution with attribution.


📌 Legal Disclaimer:


This project is an open-source implementation of a generic QR-based order fulfillment system for automated storage and retrieval.

This solution is based on standard industry practices and does not contain any proprietary information, confidential data, or trade secrets from any company.

The author developed this project independently and does not claim affiliation with any specific company or organization.

By using this software, you agree that the author holds no liability for its use in any commercial or industrial environment.


📌 Contribution & Feedback

🎯 Want to improve the project? Fork it on GitHub & submit a pull request! 🚀
