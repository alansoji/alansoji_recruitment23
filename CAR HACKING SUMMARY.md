## CHAPTER 1: UNDERSTANDING THREAT MODELS

Attack Surface:

Attack surface refers to all the possible ways to attack a target, from vulnerabilities in individual components to those that affect the entire vehicle

Finding attack Surfaces: 

List out all possible ways tht signals are recieved in the device which in this case is the carin question possible Surfaces are physical keypad ,usb port ,GPS,Bluetooth etc

Threat Modeling:

 - Level 0 (Birds Eye view):

	--Draw the vehicle in the centre and write list all the internal and external attack sufaces seperately
	

 - Level 1 (Recievers):

	-Details a specific process.It also specifies the vehicle connections tht recieve level0 output.The diagram also numbers all the recievers on basis of whether it is outside or Inside
	

 - Level 2 (Reciever Breakdown):

	-This level inspects the communication among the vehicle parts.This is also numbered based on a similar method to level 1
	
Threat Identification:
	

 - Level 0 (Birds Eye view):

	-The possible high-level threats level 0 areas follows:
	
	*Remotely take over a vehicle
		*Shut down a vehicle
		*Spy on vehicle occupants
		*Unlock a vehicle
		*Steal a vehicle
		*Track a vehicle
		*Thwart safety systems
		*Install malware on the vehicle
		

 - Level 1 (Recievers):

	-Recievers tht can be manipulated by attackes are as follows
		*Cellular Connection
		*Wi-Fi
		*Key Fob
		*Tire Pressure Monitor Sensor(TPMS)
		*Infotainment Console
		*USB
		*Bluetooth
		*Controller Area Network (CAN)

 - Level 2 (Reciever Breakdown):

	-More about identifying specific threats
		the following programs may be exploited
		*Bluez
		*wpa_supplicant
		*HSI
		*udev
		*Kvaser Driver

Threat RAting Systems:
	

 - The DREAD Rating System:

	DREAD Stands for
		*Damage potential How great is the damage?
		*Reproducibility How easy is it to reproduce?
		*Exploitability How easy is it to attack?
		*Affected users How many users are affected?
		*Discoverabilty How easy is it to find the vulnerability?
		refer table 1-1 on hackers manual for DREAD Rating Values

## CHAPTER 2: BUS PROTOCOL

Bus Protocols:

-Bus protocols govern the transfer of packets through the network of
	your vehicle. Several networks and hundreds of sensors communicate on
	these bus systems, sending messages that control how the vehicle behaves
	and what information the network knows at any given time.
	
The CAN Bus:
	
-CAN is a simple protocol used in manufacturing and in the automobile
	industry. It runs on two wires CANH(high) and CANL(low) and uses differential signalling When a signal comes can increases the voltage on one line and drops the other line an equal amount
	
The OBD-II Connector :
-OBD-II or the Diagnostic link connector(DLC) communicates with the vehicles internal network
-Its Located either above the gas pedal or the brake pedal or behind a small access panel

Finding CAN Connections:

-Hunt for wires that are 2.5V and fluctuating by a factor of 1V whis is mostly CAN
-CANH and CANL are located on pins 6 and 14 of the obd connector

CAN Bus PAcket Layout:
		

 - Standard Packet:

	-contains 4 elements
			*Arbitration ID(ID of the communicating device)
			*Identifier Extension(IDE)(always 0 for standard can)
			*Data Length Code(DLC)(Size of data 0-8 byte)
			*Data(this is the data itself)

 - Extended Packets:

	-Like standard but can be chained together to formlonger IDs
	-IDE set to 1
	
The ISO-TP Protocol:

ISO 15765-2, also known as ISO-TP, is a standard for sending packets over
		the CAN bus that extends the 8-byte CAN limit to support up to 4095 bytes by chaining CAN packets together
		
The CANopen Protocol:

-CANopen breaks down the 11-bit identifier to a 4-bit function code
and 7-bit node ID—a combination known as a communication object identifier (COB-ID).
The GMLAN Bus:
	
GMLAN is a CAN bus implementation by General Motors. It’s based on
		ISO 15765-2 ISO-TP, just like UDS (see “Unified Diagnostic Services” on
		page 54). The GMLAN bus consists of a single-wire low-speed and a dual-
		wire high-speed bus.
	
The SAE J1850 Protocol:

-The SAE J1850 protocol was originally adopted in 1994 and can still be
	found in some of today’s vehicles, for example some General Motors and
	Chrysler vehicles.
-There are 2 types of  J1850 protocols: pulse width modulation (PWM)
	and variable pulse width (VPW)
-The PWM+ an PWM- pins are located in the pins 2 and 10 on the OBD-II connector
	
The PWM Protocol:

-PWM uses differential signaling on pins 2 and 10 and is mainly used by Ford.
-It operates with a high voltage of 5V and at 41.6Kbps, and it uses dual-wire
		differential signaling, like CAN.
		
The VPW Protocol :

-VPW, a single-wire bus system, uses only pin 2 and is typically used by
		General Motors and Chrysler. VPW has a high voltage of 7V and a speed
		of 10.4Kbps.
		
The MOST Protocol:

The Media Oriented Systems Transport (MOST) protocol is designed for multi­
	media devices. Typically, MOST is laid out in a ring topology, or virtual star,
	that supports a maximum of 64 MOST devices. One MOST device acts as the
	timing master, which continuously feeds frames into the ring.
			
Each MOST frame has three channels:
	*Synchronous Streamed data (audio/video)
	*Asynchronous Packet distributed data (TCP/IP)
	*Control Control and low-speed data (HMI)
	
MOST Network Layers:
		Used to hack a cars audio and video stream.But MOST does allow access in-vehicle microphone or cell systems as well as traffic information consult fig 2-10 for the divisions of MOST
		 
MOST Control Blocks:

In MOST25, a block consists of 16 frames. A frame is 512 bits
		*Preamble 4bit
		*Boundary 4bit
		*Synchronous data
		*Asynchronous data
		*Control 2byte
		*Frame control 1byte
		*Parity 1bit
		
Hacking MOST:

MOST can be hacked from a device that already supports it, such as through
		a vehicle’s infotainment unit or via an onboard MOST controller.
		
The FlexRay Bus:

FlexRay is a high-speed bus that can communicate at speeds of up to
	10Mbps. It’s geared for time-sensitive communication, such as drive-by-
	wire, steer-by-wire, brake-by-wire, and so on
		
Hardware:

FlexRay uses twisted-pair wiring but can also support a dual-channel setup	
FlexRay implementations use only a single pair of wiring similar to CAN bus implementations

Network Topology:

FlexRay supports a standard bus topology, like CAN bus, where many ECUs run off a twisted-pair bus. It also supports star topology, like Ethernet, that can run longer segments.

Implementation:

When creating a FlexRay network, the manufacturer must tell the devices about the network setup. Recall that in a CAN network each device just needs to know the baud rate and which IDs it cares about (if any). In a bus layout,only one device can talk on the bus at a time. In the case of the CAN bus, the order of who talks first on a collision is determined by the arbitration ID.

FlexRay Cycles:

A FlexRay cycle can be viewed as a packet. The length of each cycle is determined at design time and should consist of four parts, The static segment contains reserved slots for data that always represent the same meaning. The dynamic segment slots contain data that can have different representations. The symbol window is used by the network for signaling, and the idle segment (quiet time) is used for synchronization.

Packet Layout:

The actual packet that FlexRay uses contains several fields and fits into the
cycle in the static or dynamic slot
The status bits are:
		*Reserved bit
		*Payload preamble indicator
		*NULL frame indicator
		*Sync frame indicator
		*Startup frame indicator
		
Sniffing a FlexRay Network:

Linux doesn’t have official support for FlexRay, but there are some patches from various manufacturers that add support to certain kernels and architectures there are no standard open source tools for sniffing a FlexRay network. If you need a generic tool to sniff FlexRay traffic, you currently have to go with a proprietary product that’ll cost a lot. If you want to monitor a FlexRay network without a FIBEX file, you’ll at least need to know the baud rate of the bus. Ideally, you’ll also know the cycle length (in milliseconds) and, if possible, the size of the cluster partitioning (static-to-dynamic ratio). Technically, a FlexRay cluster can have up to 1048 configurations with 74 parameters.

Automotive Ethernet:
	Because MOST and FlexRay are expensive and losing support (the FlexRay
	consortium appears to have disbanded), most newer vehicles are moving
	to Ethernet From a researcher’s perspective, the only challenge with vehicle Ethernet lies in figuring out how to talk to the Ethernet. You may need to make or
	buy a custom cable to communicate with vehicle Ethernet cables because
	they won’t look like the standard twisted-pair cables that you’d find in a
	networking closet. Typically, a connector will just be wires like the ones you
	find connected to an ECU. Don’t expect the connectors to have their own
	plug, but if they do, it won’t look like an RJ-45 connector. Some exposed
	connectors are actually round
	
OBD-II Connector Maps:

consult figures in the pdf
		
		

## CHAPTER 3: VEHICLE COMMUNICATION WITH SOCKETCAN

SocketCan interface is used to communicate with the CAN of a vehicle
SocketCAN ties into the Linux networking stack, which makes it very easy
to create tools to support CAN

Setting up can-util to connet to CAN Devices:
	sudo apt-get intall can-utils
	follow the set of commands on the pdf
	
The CAN Utilities Suite:

 1. as2log:
 2. bcmserver
 3. canbusload
 4. can-calc-bit-timing
 5. candump
 6. canfdtest
 7. cangen
 8. cangw
 9. canlogserver
 10. canplayer
 11. cansend
 12. cansniffer
 13. isotpdump
 14. isotprecv
 15. isotpsend
 16. isotpserver
 17. isotpsniffer
 18. isotptun
 19. log2asc
 20. log2long
 21. slcan_attach
 22. slcand
 23. slcanpty
 
Installing Additional Kernel Modules

Some of the more advanced and experimental commands, such as the ISO-TP–based ones, require you to install additional kernel modules, such as can-isotp, before they can be used.

U can get the additional kernel modules by using the commands provided in the pdf

Coding SocketCAN Applications

While can-utils is very robust, you’ll find that you want to write custom tools to perform specific actions.

Connecting to CAN Socket

In order to write your own utilities, you first need to connect to the CAN socket. Connecting to a CAN socket on Linux is the same as connecting to any networking socket that you might know from TCP/IP network programming.
codes related to the connection  is provided in the pdf

The Socketcan Daemon

Socketcand (https://github.com/dschanoeh/socketcand) provides a network interface into a CAN network. Although it doesn’t include can-utils, it can still be very useful, especially when developing an application in a programming language like Go that can’t set the CAN low-level socket options

Kayak

Kayak (http://kayak.2codeornot2code.org/), a Java-based GUI for CAN diagnostics and monitoring (see Figure 3-2), is one of the best tools for use with
socketcand. Kayak links with OpenStreetMaps for mapping and can handle CAN definitions. As a Java-based application, it’s platform independent, so it leans on socketcand to handle communication to the CAN transceivers.
You can download a binary package for Kayak or compile from source. In order to compile Kayak, install the latest version of Apache Maven, and clone the Kayak git repository (git://github.com/dschanoeh/Kayak). Once the clone is complete, run the commands as given in the pdf . After installing it is easy to use kayak from the terminal
Kayak can easily record and play back packet capture sessions, and it supports CAN definitions (stored in an open KDC format). As of this writing, the GUI doesn’t support creating definitions, but I’ll show how to cre-
ate definitions later.Kayak is a great open source tool that can work on any platform. In addition, it has a friendly GUI with advanced features that allow you to
define the CAN packets you see and view them graphically.


## Automotive Challenge

In ICSIM increase the speed till the end of the speedometer

 1. Requirements vcan0 , can-utils
 2. Open the Controls window and the icsim window
 3. On another terminal use cansniffer to identify the arbitary id tht varies with speed
 4. Upon finding the arbitary id of the constantly changing variable,use cansend to send a similar data packet to the icsim
 5. You may use candump log file to get an example of how a data packet looks like
 6. We observe that when we change the last three bits the speedometer flickers and by trial and error we get to the end of the speedometer

