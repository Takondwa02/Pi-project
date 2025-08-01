I.	ABSTRACT 
Tomatoes are highly perishable due to post-harvest moisture loss and microbial growth, especially in tropical climates where ambient temperatures accelerate spoilage. Traditional storage methods often fail to maintain optimal conditions, leading to significant food waste. Therefore, automated evaporative cooling system aims to preserve these farm products at low initial and running cost. 

The system will keep the temperature between 10 to 20 degrees Celsius in the storage by watering the sand surrounding the pot vessel. We have two sensors; DHT sensor which measures the temperature inside the clay vessel, ultrasonic sensor which will collect data about water level in the bucket so that the owner should refill if water goes down the preset level. We are using actuators like buzzer which will produce audible output to alert the owner about water level. LCD is to display the DHT temperature reading. 

I.I OBJECTIVES
At the end of the project, the system should be able to;
1.	Design and develop energy efficient automated evaporative system that regulates temperature based on real time clay pot environment data.
2.	Optimize water consumption by implementing algorithms that will utilize required water while maintaining cooling efficiency.
I.II KEY OUTCOMES
1.	A complete and functional protype with real time sensor - actuator thorough interaction with the external environment.
2.	Water, cost and energy efficiency data comparing this system with ordinary ways.
3.	Scalability and recommendations insights. Points explaining how the system will be used and adapted in large scale and how will it accommodate future developments.
4.	Performance evaluation report where will be the superiority of the system comparing the already existing crop cooling methods in terms of cost saving, energy and power preservation and of course people’s willingness to use the system.


II.	INTRODUCTION 
Much of the post-harvest loss of fruits and vegetables in developing countries is due to the lack of proper storage facilities. While refrigerated cool stores are the best method of preserving fruits and vegetables, they are expensive to buy and run. Consequently, in developing countries there is an interest in simple low-cost alternatives, many of which depend on evaporative cooling which is simple and does not require any external power supply (Mohammed Bah Abba, n.d). Evaporative coolers, often called "swamp coolers", are cooling systems that use only water and a blower to circulate air. When warm, dry (unsaturated) air is pulled through a water soaked pad, water is evaporated and is absorbed as water vapor into the air. The air is cooled in the process and the humidity is increased (A. Bhatia, B.E., 2020). The evaporator cooling technology is an energy-efficient alternative to compressor-based cooling.  

In hot and dry climates, with daily maximum air temperatures of 30 to 45°C, this system of evaporative cooling enables to reach temperatures between 13 and 22°C inside the cooler. The clay pot cooler can extend the shelf life of food by three to four times (Peter Rinker, 2014). This system as mostly adopted in rural areas of countries like Malawi, involves the use of clay pots that use the principle of evaporative cooling. The system is achieved with a relatively simple construction made of two differently sized clay pots, wet sand and a wet cloth. The smaller clay pot is placed inside the bigger clay pot filled with sand.  

The system owner is required to cover the opening of the smaller clay pot with a wet cloth and to now and then water the sand in between the pots. As the sand is cooled with the water, the pots also get cooled, aiding the evaporative cooling factor.  
Due to the porosity of fired clay, a part of the water can diffuse through the clay end evaporate on the outside. This evaporation process consumes thermal energy from inside of the clay pot cooler resulting in a decreasing air temperature in the inner clay pot (Peter Rinker, 2024).  
 

However, this system requires regular manual intervention, monitoring the internal temperature and ensuring the sand remains moist. These demands can reduce the effectiveness of the system, especially in rural settings where people may forget to maintain it or lack proper thermometers. 

To address these limitations, our group sought to modernize the clay pot cooler by integrating an embedded system that automates temperature sensing and sand watering. Using a Raspberry Pi 3, digital temperature sensor (DS18B20), and ultrasonic sensor (US-100), 12V solenoid valve, 5V relay switch and a buzzer, we developed a solution that not only monitors environmental conditions but also automates water replenishment and provides alerts when human intervention is needed. This approach blends traditional methods with modern IoT technology to enhance usability, consistency, and food preservation effectiveness in underserved regions. 
 
III.	THEORY 
a) Programming on Raspberry Pi 
1.	Introduction to Python for Raspberry Pi 
Python is a high-level, interpreted programming language that is user-friendly and supported extensively by the Raspberry Pi community. This language was chosen because of its strong Support on Raspberry Pi, that enabled us to use well-supported with libraries like: RPi.GPIO w1thermsensor – for reading from the DS18B20 temperature sensor and time, os, etc. – for system tasks and delays. This simplified hardware interaction, making it ideal for embedded applications. 
 
2.	Controlling GPIO pins 
The GPIO pins on the Raspberry Pi can be programmed to act as inputs or outputs. These are used to receive sensor data or control devices like sensors and relays. For this project, the following were used  • GPIO pin 4 – digital temperature sensor (DS18B20) 
•	GPIO pin 17 – ultrasonic trig pin 
•	GPIO pin 18 – ultrasonic echo pin 
•	GPIO pin 21 – relay 
•	GPIO pin 24 – buzzer 
 
3. Interfacing sensors and actuators 
Interfacing involves connecting components to GPIO pins, configuring the pins via Python, and reading or writing digital values to them. Components that needed interfacing was only the digital temperature sensor (DS18B20) that was interfaced through the 1-wire. 
 
 
b)  Interfacing, Controlling, and Communicating 
 
1.	Communication Protocols 
•	I2C (Inter-Integrated Circuit): A synchronous, multi-master protocol often used to connect low-speed peripherals. No component used this interface. 
•	SPI (Serial Peripheral Interface): High-speed synchronous protocol for short-distance communication. No component used this interfacing option. 
•	1-wire. The digital temperature sensor used this interfacing. 
•	UART (Universal Asynchronous Receiver/Transmitter): Serial communication protocol, used for debugging and peripheral interface. For this interface as well, no component used it. 
To add on, in this project, communication is mostly GPIO-based (bit-banged), suitable for simple sensors 
 
2.	Real-time data processing 
The Raspberry Pi handles real-time data from sensors through continuous loops (e.g. while True:), processing input values and acting on them with minimal delay. For example, the temperature and water level are monitored every second to decide whether to activate the relay or buzzer 
 
3.	Remote Access via SSH and VNC 
Raspberry Pi can be accessed remotely using SSH (Secure Shell) for terminal control and VNC (Virtual Network Computing) for GUI interaction. For our project, we had connected 2 devices through VNC viewer and 1 device through SSH. This enabled us to work on our project without the need to always connect to an external monitor, keyboard and mouse. 
 
IV.	TOOLS AND COMPONENTS 
A. Hardware 
•	Raspberry Pi 3 Model B 
•	DS18B20 Digital Temperature Sensor 
•	US-100 Ultrasonic Distance Sensor 
•	5V Relay Module 
•	Solenoid valve 
•	Buzzer 
•	Resistors (1KΩ’s, 10kΩ, 4.7kΩ) 
•	Breadboard and jumper wires 
•	Power supply (12V) 
 
B. SOFTWARE 
•	Python 3 
•	Thonny IDE: User-friendly Python editor for Raspberry Pi 
•	Proteus: For circuit simulation and design diagrams 
•	Raspbian OS (Raspberry Pi OS) 
 
V.	PROCEDURE 
A.	Simulation 
 
 
B.	Prototyping   
VI.	RESULTS 
After running the code on Thonny, DHT sensor displayed temperature changes according to the clay temperature. Relay also showed the status (if it is on or off). 
The ultrasonic sensor was able to show changing water level as it was being watered out.  
Below are the images supporting the above explanations. 
 
Figure 2 The system in use
 
 
Figure 3 Results after running Python code on Thonny IDE
VI.I PERFORMANCE ANALYSIS
From figure 3 above, top lines of the code explain refilling of the water as the bucket was normally empty and the buzzer was off upon refill. The process is happening simultaneously with temperature measurement by the DHT sensor based on real time. 
It can be seen that the temperature kept dropping below 20 degrees Celsius which the upper threshold.
The relay on at temperature 20.94 degrees because the temperature went above 20 and there was the need to open the valve (requiring 12V while the pi provided maximum power of 5V, thus the usage of relay to dynamically switch based on what has to be done). 
When the system started cooling below 20 degrees, the relay is of till the end based on the figure 3 above.
The ultrasonic sensor is always active giving data about water level in the bucket, thus the phrase water level distance is: in the code.

 
VII.	CONCLUSION 
Automated Evaporative cooling system saves to preserve tomatoes by keeping it a cold storage between 10-to-20-degree Celsius so that farmers can maximize production while using low power, initial and running cost. 
The logic is when the temperature goes above 20 degrees, DHT temperature sensor collect this change in environment and sends data to the chip controller which commands the valve to open water pipe and then soil gets moistened. The system will allow water to flow from the bucket with the work of the valves on the water pipe into the soil covering the pot containing tomatoes.  
When the temperature stabilizes, DHT sensor collect the data and sends it the processor which sends command signals to close the valve. 
In the case that water level has dropped below the programmed, ultrasonic sensor detects that and send the data to the processor which then commands the actuator (buzzer) to ring and the farmer is able to refill the bucket with water. 
VII.I CHALLENGES
1.	We planned to use solar cells as our main supplying power and batteries as backup but the resources were unavailable.
2.	Faulty components like jumpers, relay.
3.	We planned to use soil moisture sensor so that it should be incorporated in the soil for efficient data collection but we had problems in signal conditioning where we tried to use ADC, later we used the DHT temperature sensor which can not be put into the soil.
VII.II FUTURE IMPROVEMENTS
1.	Soil moisture sensor could be used to effectively collect data without delays. 
2.	Solar cells could be in use and batteries being charged from the solar energy which will be later used as backup when sun go set.
3.	Water bucket containing water to moist the soil surrounding the crops could be linked to a big water reservoir so that farmers attention should reduced as when the waterproof water sensor detects water deficiency, it should open tap valve and allow water fill the bucket right away from the reservoir.
 
VIII.	RECOMMENDATIONS  
The project can be improved by using soil moisture sensor to measure humidity alongside the temperature parameter. The measurements used could be humidity values to determine moisture content in the soil. 
The system can be implemented in large industry using heavy solar power and batteries.
Also, waterproof ultrasonic sensor can be used in place of the sensor we used as it can damage when get in touch with water somehow.
