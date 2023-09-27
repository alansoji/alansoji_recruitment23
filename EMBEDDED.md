﻿## Embedded

## Basics of Arduino

Arduino is tool that helps you control electronic stuff with code


## Basic Serial Communication Protocol

Types of Communication Protocol:
 - Synchronous Comunication Protocol
 - Asynchronous Comunication Protocol

   ## UART (Universal Asynchronous Receiver Transmitter)
1.  **Asynchronous Communication Protocol**: UART employs an asynchronous communication protocol, where data transmission does not rely on a shared clock signal between the communicating devices.
    
2.  **Ad-Hoc Topology**: UART does not adhere to a specific network topology and is adaptable to various system configurations, operating effectively in ad-hoc setups.
    
3.  **Component Structure**: UART comprises two fundamental components: the Transmitter, responsible for sending data, and the Receiver, tasked with receiving transmitted data.
    
4.  **Start and Stop Bits**: Each data transmission in UART begins with a start bit and concludes with a stop bit, framing the actual data for accurate reception.
    
5.  **Baud Rate Definition**: UART employs a baud rate, specifying the transmission speed at which data is sent and received. Synchronization necessitates both the transmitter and receiver to operate at the same baud rate.
    
6.  **Configurability**: UART possesses a high degree of configurability, allowing customization of parameters such as data bits, parity, and stop bits to suit specific communication requirements.
    
7.  **Reliable Communication within Limited Ranges**: UART communication is notably reliable for short to moderate distances, ensuring dependable data transfer within specified ranges.
    
8.  **Embedded Systems Integration**: UART finds extensive application in embedded systems, facilitating communication between microcontrollers, sensors, display modules, GPS modules, and various other peripheral devices.
    
9.  **Diverse Applications**: Additionally, UART serves as a pivotal communication interface for interaction between computers and external equipment, showcasing its versatility and widespread usage.

      Programming Approach

      Bit Banging:
      Bit banging is a method of serial communication used in microcontroller and embedded systems 							 programming. It involves manually controlling the state of individual digital pins to transmit or receive data without relying on dedicated hardware communication peripherals like UART, SPI, or I2C. Instead, the          microcontroller or embedded system's firmware directly manipulates the pins to send or receive individual bits of data.

      UART Peripherals:
      It ia method in which the Transmit register transfers full data to shift register and the shift register and it transfers this data byte by byte to the
      next device were the process is called parallel in serial out. The shift register of the next device collect the data one by one and transfer it to the
      receiver register all at once were the process is called serial in parallel out.

      Advantages of UART:
      - Easy to interface
      - Less Hardware
      - Less Software Complications

      Disadvantages of UART
      - Synchronizing Baud Rate
      - Only two devices can be connected
      - No Acknowledgement
        
   ## I2C (Inter-Integrated Circuit)

 - **Origin and Basics**: I2C is a way for devices to talk to each other. It was made by Philips.

 -   **Two Wires**: It uses just two wires - one for messages (SDA) and one for timing (SCL).
    
 -   **Master and Slaves**: There's a main boss (master) and other workers (slaves) in this system.
    
 -   **Two-Way Traffic**: The boss and workers can talk back and forth using those two wires.
    
 -   **Address for Each Worker**: Each worker has its own special name (address) so the boss can talk to a specific worker.
    
 -   **Boss Sets the Beat**: The boss controls the timing, making sure everyone is on the same page.
    
 -   **Messages in Bytes**: Information is sent in chunks of 8 bits (bytes).
    
 -   **Saying "Got It"**: After each chunk, the worker says "got it" or "not got it" to the boss.
    
 -   **Different Speeds**: They can talk fast or slow, depending on what they're doing.
    
 -   **Short-Distance Chat**: It's good for talking to neighbors, not for shouting across the town.
    
 -   **Simple Compared to Others**: It's easier to use than some other talking methods.
 
  Bus Arbitration:
   
   It is the process of determining which device on the I2C bus gets to transmit data or initiate a communication transaction when multiple devices are connected to the same bus. I2C is a multi-master communication protocol, which means that multiple devices can be connected to the same bus, and they can all act as both masters and slaves. As a result, there needs to be a way to resolve conflicts when multiple devices try to communicate simultaneously.
   Clock Stretching:
   It a feature that allows one of the devices on the bus, typically the slave device, to temporarily hold the SCL (Serial Clock) line low to slow down the master device's clock when it needs more time to process data. This helps in preventing data overrun and ensuring reliable communication between devices with potentially different processing speeds or response times.
   
   Advantages of I2C
 - Two wires only
 - Multimater Compatibility
 - Better Error Handling
 - Different mode flexibility for Slave

   Disadvantages of I2C
 - Less Flexibility for Slave address
 - Complexity of Firmware
 - Increased Data Overhead
 - Hardware Limitations
 - Bus Topology
   ## SPI (Serial Perpheral Interface)
1.  **Synchronous Communication Protocol**: SPI operates as a synchronous communication protocol, requiring synchronized timing between the transmitting and receiving devices.
    
2.  **Support for Multiple Slave Devices**: The SPI protocol is designed to accommodate multiple slave devices connected to the same bus. Each slave device possesses a unique chip select (CS) or slave select (SS) line, enabling the master to designate a specific slave for communication.
    
3.  **Full-Duplex Communication**: SPI supports full-duplex communication, allowing simultaneous data transmission in both directions. This capability is facilitated by dedicated data lines: MOSI (Master Out Slave In) for master-to-slave data transmission and MISO (Master In Slave Out) for slave-to-master data transmission.
    
4.  **Serial, Bit-by-Bit Data Transfer**: SPI transfers data serially, transmitting one bit at a time. The data bits are sent sequentially over the MOSI and MISO lines. Data is commonly sent in chunks of 8 or 16 bits, although the word size can be configured based on the specific devices involved.
    
5.  **Clock Configuration Modes**: SPI supports two clock configuration modes, namely CPOL (Clock Polarity) and CPHA (Clock Phase), providing flexibility in clock signal characteristics to suit different device requirements.
    
6.  **Pin Configuration**: Typically, SPI implementations involve at least four pins: MOSI for data transmission, MISO for data reception, SCLK (Serial Clock) for synchronization, and SS/CS (Slave Select/Chip Select) to designate the target slave device.
    
7.  **No Addressing in Data Packets**: In contrast to I2C, SPI does not incorporate addressing within the data packets. Instead, the master selects a specific slave for communication by asserting the relevant CS/SS line.
    
8.  **Suitability for Short-Distance Communication**: SPI is well-suited for short-distance communication, typically within a single Printed Circuit Board (PCB) or between closely located devices.
    
9.  **Minimal Protocol Overhead**: SPI exhibits minimal protocol overhead as it omits addressing and acknowledgment signals, streamlining the communication process and enhancing efficiency.

   Advantages of SPI
 - Low Power Consumption
 - SPI is faster than I2C
 - Easy to Interface
 - Different Modes of Transmission

   Disadvantages of SPI
 - Atleast 4 connections are required
 - Does not support Multimaster
 - More GPIOs for more Slaves
     
   ## CAN (Control Area Network)
1.  **Asynchronous Communication Protocol with a Notable Originator**: CAN (Controller Area Network) is an asynchronous communication protocol initially conceived by Robert Bosch.
    
2.  **Two-Wire Bus System for Data Transmission and Reception**: CAN typically employs a two-wire bus system: one wire for transmitting data (CAN-High or CAN-H) and another for receiving data (CAN-Low or CAN-L).
    
3.  **EMI Reduction and Reliable Data Transfer**: CAN architecture is designed to minimize electromagnetic interference (EMI) and ensure consistent and reliable data transfer.
    
4.  **Multi-Master Architecture for Concurrent Data Transmission and Reception**: CAN supports a multi-master architecture, allowing multiple Electronic Control Units (ECUs) to simultaneously transmit and receive data on the same bus without a centralized master controller.
    
5.  **Deterministic Communication with Predictable Transmission Time**: CAN provides deterministic communication, offering messages with a predictable and guaranteed transmission time.
    
6.  **Message-Based Communication Model with Priority Identification**: CAN adopts a message-based communication model, organizing data into frames with unique identifiers (IDs) that determine message priority and content.
    
7.  **Non-Destructive Bitwise Arbitration for Data Transmission Priority**: CAN utilizes a non-destructive bitwise arbitration mechanism to establish data transmission priority when multiple nodes attempt to send messages concurrently.
    
8.  **Incorporated Error Detection and Handling Mechanisms**: CAN integrates error detection and handling mechanisms within its protocol. Nodes actively monitor the bus for errors such as bit errors, frame errors, and other fault conditions, and take corrective actions or retransmit data accordingly.
    
9.  **Message Prioritization Using CAN Identifier (ID)**: CAN enables message prioritization through the CAN identifier (ID), where lower ID values represent higher-priority messages, ensuring critical data is transmitted ahead of less critical data.
    
10.  **Extensibility and Scalability for Varied Applications**: CAN is extensible and scalable, catering to a wide range of applications. CAN networks can vary in size from a few nodes to hundreds or thousands interconnected through bridges or gateways.
    
11.  **Fault Tolerance with Operational Continuity**: The CAN network can maintain operation even in the presence of node failures, ensuring system resilience.
    
12.  **Prominent Application in Automotive Industry**: CAN finds extensive use in the automotive industry, particularly in applications like engine control, vehicle diagnostics, and infotainment systems.
    
13.  **Standardization under ISO 11898**: CAN adheres to standardization defined by ISO 11898, encompassing physical and data-link layer specifications.
    
14.  **Renowned for High Reliability and Robustness**: CAN is widely recognized for its high reliability and robustness, rendering it suitable for demanding environments characterized by noise and harsh conditions.

   
   
## Arduino Challenges
   ## 1.Push Button Controlled Traffic Light
   
   1.Simple circuit tht blinks red when pressed once yellow when pressed twice and green when pressed thrice.
   2.Components required: Arduino Uno(AU), Red LED, Yellow LED, Green LED, 3 100 ohm resistor, Push  Button, 10k ohm resistor, Connecting Wires.   
   3.Connect +ve terminal of the leds to digital pins and negative terminals to resistors connected to ground.
   4.Connect the 1b of the push button to the positive line of the breadboard and 2a to the resistor  connecting to the ground and to the Digital pin.
   5.Provide the voltage and ground lines to the arduino
   6.Code of the program can be found here : https://www.tinkercad.com/things/fTGGaq7U7ay-bi0s-1/editel?sharecode=wSzCGNAlEDgmS42qSxWAChMbQL45_4ThrevXqURgEhA
   
   ## 2.Servo Motor Movement based of potentiometer value
   
   1.Servo motor moves according to potentiometer value.
   2.Components:Servo motor,Potentiometer,ARDUINO UNO,connecting wires,Breadboard.
   3.Connect the ground and power of potentiometer accordingly and afterwards connect the output pin to analogue pin A0 on the arduino.
   3.Similarly connect the ground and power to the servo meter and connect the middle pin to the Digital pin(~PWM).
   4.The code associated can be obtained here:https://www.tinkercad.com/things/4tP7qeHpVUw-bi0s-2/editel?sharecode=u7rrbAj9Rax1ahm8cYE2fUk-Sed4z0_YO8oCmG1OG3I
   
   ## 2.LCD Quiz
   
   1.Complex circuit with I2C LCD board and code logic requirements.
   2.Components:LCD 16X2 (I2C),ARDUINO UNO, 4 push buttons,Resistors 10k ohm X4,Breadboard,Connecting  Wires.
   3.Connect the voltage line to the 1b of each push buttons and connect the resistors from the ground line to 2a.
   4.Connect the input lines from 2a of the resistors to the digital pins of the ARDUINO UNO.
   5.The Code assosiated with the challenge can be found here:https://www.tinkercad.com/things/hvScZ7eJ1YZ-bi0s-3/editel?sharecode=ym304V63kV2VjdppHrmpSrGTSTzRWJM0YoQ7DUsgapw
   
## Arduino Practice Projects
   ## 1.Temperature Sensitive Fan:
   1.A fan tht increases speed depending on the temperature.
   2.Components:ARDUINO UNO,TMP36,DC Motor.
   3.Connect the groung and power wires of the tmp36 to the groung and power of arduino,Similarly connect the ground of the fan to the Arduino GND and the power pin to the digital output pin.
   4.Connect the signal wire to the analogue A0 of the ide.
   5.The assosiated code is given here:https://www.tinkercad.com/things/bpABWoKy0fa-fan/editel?sharecode=gaNiZGu6cxTSrnRvcRs-oqfvvOn3iY4H5OXkQ7ovAFk
   
   ## 2.Photo Sensitive LED
   1.An Led tht depends on th amount of light in the surroundings.
   2.Components:LED,Photoresistor,Resistor 10 ohm,ARDUINO UNO.
   3.Connect The ground of the led to the Breadboard ground line and the power to the digital(~PWM) pin of the arduino.
   4.Similarly Connect the power pin of the Photoresistor to the resistor and connect the resistor to power line of the breadboard.
   5.Connect the input wire to the power pin of the photoresistor and connect it to the analog pin
   A0.
   6.The Code of the programme can be found here:https://www.tinkercad.com/things/0SMilVXJbBV-photosensitive-lighting/editel?sharecode=r5XVjiKtlub4iIVE4-bzdKC9fbiKMIRKr2n3_eziXNA
   
   ## 3.Distance Detector
   1.Three LEDs tht light up depending on the distance from the sensor.
   2.Components:Ultrasonic Distance Sensor,LED X3,ARDUINO UNO.
   3.Connect the GND and Power of the sensor to the GND and power of the ARDUINO.
   4.Connect the ground of the LEDS to the GND of the ARDUINO and the power of leds to individual  digital pins.
   5.The code for this challenge can be accessed here:https://www.tinkercad.com/things/2FDnhCUIwN2-fantastic-krunk-lahdi/editel?sharecode=nPSnrl4eBnNO3Q49A0OLQz7ia3cCfBr1yh8u8Aq-VPo.lahdi/editel?sharecode=nPSnrl4eBnNO3Q49A0OLQz7ia3cCfBr1yh8u8Aq-VPo.
