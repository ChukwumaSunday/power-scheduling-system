# Proposal/Report on Power Scheduling Project Using LDR with Arduino Nano for Solar Energy Management

Introduction
Energy management is a crucial aspect of modern office operations, especially with the growing need for sustainable energy solutions. This project outlines the design and implementation of a power scheduling system that uses an Arduino Nano, Light Dependent Resistor (LDR), DS1307 Real-Time Clock (RTC) module, and relays to optimize the use of solar energy in carrying heavy electrical loads during periods of high sunlight intensity. The system also incorporates a 2x16 Liquid Crystal Display (LCD) for real-time data visualization and a user interface with five control buttons for manual adjustments.

Objective
The primary objective of this project is to implement an automated system that shifts heavy electrical loads in an office setting to solar power when sunlight intensity is sufficient. This will minimize dependence on conventional grid power, reduce energy costs, and promote the use of renewable energy.

System Components
1. Arduino Nano: The microcontroller used to process sensor data and control the relays.
2. LDR (Light Dependent Resistor): A sensor used to measure sunlight intensity. The system uses its input to determine when sufficient sunlight is available to switch loads to solar energy.
3. DS1307 RTC Module: Provides accurate time tracking, enabling the system to record start time, date, and manage scheduled tasks.
4. 12V DC Relay and AC Relay: These relays act as switches for controlling the AC-powered heavy loads. The DC relay activates the AC relay, allowing it to handle the higher voltage loads.
5. 2x16 LCD Display: Used for displaying real-time data such as sunlight intensity, load status, and current time.
6. 5-Button Interface (Up, Down, Left, Right, Select): These buttons allow for manual adjustments, navigation of the menu, and control of the system settings.
7. Solar Panel and Battery: The solar panel generates the energy, while the battery stores excess energy for later use.

System Design
The power scheduling system is designed to operate as follows:

 
The Schematics



![image](https://github.com/user-attachments/assets/1d842541-6ea9-4357-b44b-d86c63a82211)


 
The Board Layout




 
The Board Front View

 
The Board Back View

LDR-Based Sunlight Monitoring
The LDR is connected to the Arduino Nano to measure the ambient light intensity. When sunlight is intense enough, typically indicated by an analog voltage value crossing a predefined threshold, the system activates the relays to switch the heavy loads to solar power.

Relay Control
The 12V DC relay is used to switch the AC relay, which controls the connection of heavy electrical loads to the solar power system. When sufficient sunlight is detected, the Arduino activates the DC relay, which in turn energizes the AC relay, allowing heavy office appliances such as air conditioners or industrial lighting systems to run on solar power.

Real-Time Clock for Scheduling
The DS1307 RTC module is employed to keep track of the date and time. This allows the system to monitor power consumption periods, maintain a record of when loads are shifted to solar energy, and ensure that power switching happens during predefined hours of operation. 

The RTC is also crucial for scheduled load management, ensuring that the system operates within the designated timeframes to prevent unnecessary switching during nighttime or low sunlight conditions.

User Interface and LCD Display
The 2x16 LCD displays the current system status, including:
- Sunlight intensity level
- Power source in use (Grid vs. Solar)
- Current date and time from the RTC
- Load status (On/Off)

A 5-button control system allows for easy navigation through the user interface, where the user can manually configure settings such as:
- Sunlight intensity threshold
- Start and stop times for solar-based operation
- Load priorities

Button Functions
- Up/Down Buttons: Used to navigate through menu options.
- Left/Right Buttons: Used to adjust values such as thresholds or time settings.
- Select Button: Used to confirm selections and save settings.

 System Flowchart
1. Initialization: System starts, RTC module initializes, and LCD displays current status.
2. Sunlight Measurement: The Arduino reads LDR values and compares them to the set threshold.
3. Decision Logic:
   - If the sunlight intensity exceeds the threshold, the DC relay is activated to switch the heavy loads to utilizes the solar power.
   - If sunlight intensity is below the threshold, the system defaults to grid power.
4. Manual Override: Users can manually control load settings through the button interface.
5. Scheduled Operation: The RTC module ensures that load switching only occurs within defined operational hours.

Software Implementation
The system software is written in C/C++ and developed using the Arduino IDE. Key sections of the software include:
1. LDR Sensor Data Processing: The LDR provides analog input values, which are converted into digital values for comparison against a predefined threshold.
2. RTC Time Management: The DS1307 module communicates with the Arduino via I2C protocol to maintain accurate time.
3. Relay Control: The Arduino outputs a signal to the DC relay based on the LDR sensor input and the time constraints defined by the RTC module.
4. LCD Display Interface: The LiquidCrystal library is used to manage the 2x16 LCD, allowing for the display of real-time data and system status.
5. Button Interface: Interrupts and debouncing techniques are used to ensure smooth navigation and control via the five-button interface.
Required Components

S/N	COMPONENT	QUANTITY	UNIT PRICE	COST (N)
1	Arduino Nano	1	4,000	4,000
2	BC337	2	50	100
3	6 pins connector	1	200	200
4	7805 Voltage Regulator	1	200	200
5	LED	2	50	50
6	Trim Resistor 10k	2	200	400
7	LDR	1	1,000	1,000
8	12V Adapter	1	2,500	2,500
9	Glossy Paper	4	50	200
10	PCB	1	1,000	1,000
11	DS1307 RTC + CR2032 Cell	1	1,300	1,300
12	12v DC Relay	1	450	450
13	AC  Relay	1	1,500	1,500
14	2x16 LCD	1	2,500	2,500
15	Connecting Wire		2,500	2,500
16	Black Screw	6	50	300
17	Button	5	100	500
18	Resistors	9	20	180
20	Capacitors	4	50	200
21	Male Jumper	1	200	200
22	Female Jumper	1	200	200
23	Blocking Diode	1	50	50
24	Casing/Box	1	1,500	1,500
	Total			21,000


Advantages
- Energy Savings: By utilizing solar energy during peak sunlight hours, the system reduces reliance on grid power, leading to lower energy costs.
- Sustainability: This project promotes the use of renewable energy, contributing to a greener office environment.
- Automation: The system requires minimal human intervention, making energy management more efficient and reliable.
- Cost Efficiency: Once installed, the system reduces operational costs by utilizing free solar energy for heavy loads.

Challenges and Solutions
1. Sunlight Variability: Fluctuating weather conditions may affect sunlight intensity. To address this, the system allows manual configuration of the sunlight threshold via the button interface.
2. Power Backup: In the event of low solar power, the system automatically switches back to grid power, ensuring continuous operation of heavy loads.

Conclusion
This project demonstrates an efficient method for managing power consumption in an office setting by utilizing renewable solar energy when available. Through the use of an LDR, RTC module, relays, and a user-friendly interface, the system provides a cost-effective and environmentally friendly solution for energy management. By incorporating automation and user-configurable settings, the system offers flexibility while promoting sustainability.

The next step is to refine the system with real-world testing to ensure stability and performance in various environmental conditions.

---

This report provides a detailed overview of the system design and operation. If you need further technical details or specific code snippets, let me know!
