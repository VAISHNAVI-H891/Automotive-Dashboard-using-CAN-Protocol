# 🚘 Automotive-Dashboard-using-CAN-Protocol

📖 Overview

This project implements a multi-ECU automotive system simulation using the Controller Area Network (CAN) protocol.
It models real-time interaction between vehicle subsystems such as Engine Control, Transmission Control, and Dashboard Display, similar to modern automotive electronic architecture.

The system is developed using the PIC18F4580 (CAN-enabled microcontroller) and demonstrates real-time data acquisition, processing, and inter-ECU communication.

🧠 System Architecture

ECU Network Structure

Driver Input
     ↓
ECU1 (RPM & Indicators)
ECU2 (Speed & Gear)
     ↓
   CAN Bus
     ↓
ECU3 (Dashboard Display)
ECU	Responsibility
ECU1	Engine RPM & Indicator Control
ECU2	Vehicle Speed & Gear Management
ECU3	Dashboard Display & Status Indication
⚙️ Functional Modules
🔹 ECU1 – Engine & Indicator Control

RPM simulation using potentiometer (0 – 6000 RPM)

Indicator control via switches:

⬅️ Left

➡️ Right

⚠️ Hazard

⛔ Off

Transmits RPM and indicator status over CAN

🔹 ECU2 – Speed & Transmission Control

Speed simulation using potentiometer (0 – 100 km/h)

Gear selection:

N, 1, 2, 3, 4, 5, R

Safety logic:
⚠️ Speed increase restricted in Neutral

Broadcasts speed and gear data via CAN

🔹 ECU3 – Dashboard ECU

Receives CAN messages

Displays:

📟 RPM

🚗 Speed

⚙️ Gear Position

Controls indicator LEDs

📨 CAN Communication
Parameter	CAN ID
RPM	0x10
Speed	0x20
Gear	0x30
Indicators	0x40

✔ Periodic transmission
✔ Shared CAN bus network
✔ Standard frame communication

🔧 Hardware Components

🧩 PIC18F4580 (CAN-enabled MCU)

🔌 CAN Transceiver

🎛 Potentiometers (Analog inputs)

🔘 DKP Switches (Digital inputs)

💡 LEDs (Indicator output)

📟 CLCD (Dashboard display)

🔋 Power Supply

💻 Software Structure

ECU1----->

* ADC Driver

* Switch Interface

* RPM Processing

* Indicator Control

CAN Transmit

* ECU2 ----->

* ADC Driver

* Speed Calculation

* Gear Logic

CAN Transmit

ECU3 ----->

CAN Receive

* Data Parsing

* CLCD Display

* LED Control

📊 Data Processing
RPM   = (ADC_Value / 1023) × 6000
Speed = (ADC_Value / 1023) × 100

✔ Analog input converted to engineering units
✔ Data packed into CAN payload

⭐ Key Features

✔ Multi-ECU CAN network implementation
✔ Real-time embedded system operation
✔ Modular driver-based firmware
✔ Analog + Digital input handling
✔ Dashboard visualization
✔ Automotive architecture simulation

🎯 Applications

-->Automotive Embedded Systems learning

-->CAN protocol implementation

-->ECU communication architecture study

🚀 Future Enhancements

-->CAN error handling & diagnostics

-->OBD / UDS simulation

-->Fuel & temperature monitoring

-->PC-based CAN monitoring interface

-->RTOS integration

👨‍💻 Author

Vaishnavi
