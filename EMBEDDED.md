## Embedded

## Basics of Arduino

Arduino is tool that helps you control electronic stuff with code

   ## Arduino Trifecta
   
   1. Hardware
   2. IDE
   3. Code

## Basic Serial Communication Protocol

Types of Communication Protocol:
1. Synchronous Comunication Protocol(SPI,I2C)
2. Asynchronous Comunication Protocol(UART,CAN)

   ## UART (Universal Asynchronous Receiver Transmitter)
   1. It is an Asynchronous Communication Protocol.
   2. Is ia Ad-Hoc type of Topology.
   3. It consist of two main components:Transmitter and Receiver.
   4. It uses Start bit and Stop bit before and after each transmission of data.
   5. It has Baud rate that defines the speed at which data is transmitted and both transmitter and receiver should be on same baud rate.
   6. UART is highly configurable.
   7. UART communication is reliable for short to moderate distances.
   8. UART is commonly used in embedded systems for communication between microcontrollers, sensors, display modules, GPS modules, and other peripheral devices.
   9. It is also used for communication with computers and other external equipment.

      Programming Approach

      Bit Banging:
      Bit banging is a method of serial communication used in microcontroller and embedded systems 							 programming. It involves manually controlling the state of individual digital pins to transmit or receive data without relying on dedicated hardware communication peripherals like UART, SPI, or I2C. Instead, the          microcontroller or embedded system's firmware directly manipulates the pins to send or receive individual bits of data.

      UART Peripherals:
      It ia method in which the Transmit register transfers full data to shift register and the shift register and it transfers this data byte by byte to the
      next device were the process is called parallel in serial out. The shift register of the next device collect the data one by one and transfer it to the
      receiver register all at once were the process is called serial in parallel out.

      UART Configuration

      1. Clock configuration
      2. Data Loading
      3. Data Transmission
      4. Monitor data: Looping Method or Interrupt Method

      Advantages of UART:
      - Easy to interface
      - Less Hardware
      - Less Software Complications

      Disadvantages of UART
      - Synchronizing Baud Rate
      - Only two devices can be connected
      - No Acknowledgement
        
   ## I2C (Inter-Integrated Circuit)

   1. It is a Synchronous Comunication Protocol, invented by Philips.
   2. I2C uses only two wires for communication - one for data (SDA) and one for the clock (SCL).
   3. I2C network uses master-slave architecture, there is one master device and one or more slave devices.
   4. Both the data (SDA) and clock (SCL) lines are bidirectional, allowing data to flow in both directions between the master and slave devices
   5. Each slave device on the bus has a unique 7-bit or 10-bit address, allowing the master to select a specific device for communication.
   6. The master device generates the clock signal (SCL), ensuring synchronization of data transmission between devices.
   7. Data is transferred in frames, with each frame consisting of 8 bits (1 byte). It may include a 9th bit for acknowledgment or other purposes.
   8. After each byte of data is sent, the receiving device acknowledges its successful reception by pulling the SDA line low (ACK) or leaving it high (NACK) to signal an error or end of communication.
   9. I2C supports multiple clock speeds, such as standard mode (100 kbps), fast mode (400 kbps), and high-speed mode (up to 3.4 Mbps)
   10. I2C is suitable for short-distance communication within a single board or between closely located devices due to its limited range.
   11. I2C is relatively simple compared to other communication protocols like SPI or UART.
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

   1. It is a Synchronous Comunication Protocol.
   2. SPI supports multiple slave devices on the same bus.
   3. Each slave device has a unique chip select (CS) or slave select (SS) line that the master uses to select the specific slave with which it wants to communicate.
   4. SPI allows for full-duplex communication, which means that data can be transmitted in both directions simultaneously.This is achieved by having separate data lines for sending data from the master to the slave (MOSI - Master Out Slave In) and from the slave to the master (MISO - Master In Slave Out).
   5.  SPI transfers data serially, one bit at a time. The data bits are sent sequentially over the MOSI and MISO lines. Data is usually sent in 8-bit or 16-bit chunks, but the word size can be configured based on the devices involved.
   6. SPI supports two clock configuration modes: CPOL (Clock Polarity) and CPHA (Clock Phase).
   7. SPI usually consists of at least four pins: MOSI, MISO, SCLK (Serial Clock), and SS/CS (Slave Select/Chip Select).
   8. Unlike I2C, SPI does not involve addressing in the data packets. The master selects a specific slave by asserting the appropriate CS/SS line.
   9. SPI is suitable for short-distance communication, typically within a single PCB (Printed Circuit Board) or between closely located devices.
   10. SPI has minimal protocol overhead since it does not include addressing or acknowledgment signals.

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

   1. It is an Asynchronous Communication Protocol, invented by Robert Bosch.
   2. CAN typically uses a two-wire bus system: one wire for transmitting data (CAN-High or CAN-H) and one wire for receiving data (CAN-Low or CAN-L).
   3. It helps to reduce electromagnetic interference (EMI) and ensures reliable data transfer.
   4. CAN supports a multi-master architecture, meaning that multiple ECUs can simultaneously transmit and receive data on the same bus without a centralized master controller.
   5. CAN offers deterministic communication, meaning that messages have a predictable and guaranteed transmission time.
   6. CAN uses a message-based communication model. Data is organized into frames, with each frame containing an identifier (ID) that defines the message's priority and content.
   7. CAN uses a non-destructive bitwise arbitration mechanism to determine which node gets to transmit data when multiple nodes attempt to send messages simultaneously.
   8. CAN incorporates built-in error detection and handling mechanisms. Nodes monitor the bus for errors such as bit errors, frame errors, and other fault conditions. When errors occur, nodes can retransmit       data or take appropriate actions.
   9. CAN allows for message prioritization using the CAN identifier (ID). Lower ID values represent higher-priority messages, which ensures critical data is transmitted before less critical data.
   10. CAN is extensible and scalable, making it suitable for a wide range of applications. CAN networks can range from a few nodes to hundreds or even thousands of nodes interconnected through bridges or          gateways.
   11. Can network can continue to operate even if one or more nodes fail.
   12. CAN is widely used in the automotive industry for various applications, including engine control, vehicle diagnostics, and infotainment systems.
   13. CAN is standardized under ISO 11898, which defines the physical and data-link layer specifications.
   14. CAN is known for its high reliability and robustness, making it suitable for demanding environments where noise and harsh conditions are common.
   
   
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
