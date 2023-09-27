

## **Subsection 1:**

OT Security:

Operational technology (OT) is the use of hardware and software to monitor and control physical
	processes, 	devices, and infrastructure pOT SEC is the practices and technologies used to (a) protect people, assets, and 	information, (b) monitor and/or control physical devices, processes and events, and (c) initiate state 		changes to enterprise OT systems.

Exapmles of ICS:

 

 - (SCADA) supervisory control and data acquisition

	collect data from sensors and sends it to a central computer tht controls and manages thge data
	

 - (DCS) distributed control systems

	used to manage locl controlleres in one location

effective ot sec is non negotioable
requirements of ot sec vendor :
		

 - identify and classify assets

		

 - segment the network

		

 - analyze traffic for threats

		

 - control identity and acess management

		

 - secure wired and wireless connectins

Benefits of security fabric:
		

 - visibility :

	-defining attack surfaces and classifying them on basis of security
			OT security teams can dictate allowed traffic, ports, protocols, applications, and services.
		

 - Control :

	-Multifactor authentication ensures the appropriate people have the appropriate assigned 			permissions and access  
		-Network segmentation and micro-segmentation provide a layered and leveled approach with 			zones of control
			-Sandboxing detects threats on the OT network and automated quarantine prevents them from 			doing damage
		

 - Continuous Monitoring :

	-Continuous analysis of behaviors in OT networks helps teams learn what, where, when, who, 		and how by gathering intelligence about known and unknown threats

## Subsection 2:

IT vs OT :

-IT collection of data while OT operaties with machines

Why is ot at risk :

-IT OT convergance leads to efficiency but connects it to the internet thus opening up risks

Challenges in ot security:
	

 - lack od skill in Soc(security operation centre)

	

 - changing adverserial tactics

	

 - need of different tools(no single tool and skills can provide
   visibility to all threats

	

 - passive and manual tooling(cannot automatically order shutdown)

	

 - old equipment exposed endpoints

Securing the Ot environment:
	

 - secure access

	

 - management of assets

	

 - software vulnerability analysis

	

 - management of patching

	

 - dividing network into subsegments

	

 - Backup of data

## Subsection 3:

Acess Control:

-Regulating who can acess the different security aspects of an ot
-types include physical and logical
-physical acess control involves limiting acess to buildings etc while logical acess control involve limiting acess to 
-connections computer networks etc

Importance of access control:

-prevenst unauthorized acess and thus prevents security breach

How it works:

-identifies certain user using credentials/keys/biometrics and determines the level of access 			provided to the individual Lightweight Directory Access Protocol and Security Assertion Markup Language are protocols 			which provide access control for authentification
			
Types of acess controls:

 - MAndatory access control(MAC):access rights maintained by a singular
   authority based on 			multiple level security mosty on gov and
   military environments
 - Discretionary Access Control(DAC):This is an access control method in
   which owners or 				administrators of the protected system, data or
   resource set the policies defining who or what is 			 			authorized
   to access the resource
 - role based access control(RBAC):security clearance based on roles not
   individual,can be used to enforce MAC and DAC frameworks
 - Attribute BAsed Access Control:MAnages Access rights by evaluating a
   set of rules using the attributes of the user

Impelementing access controls:
	
-access management systtems provide access control software user database and control policies


## Subsection 4:

PLOP:

-PLOP or the principle of least privilage is the idea tht any user program or process should have only the bare minimum privileges necessary to perform its function

How PLOP works:

-allowing only enough access to a user necessary only to do their respective functions

Examples of PLOP:

-user accounts with least privilege
	-Mysql accounts with ;least privilege
	-Just in time least privilege

Benefits of PLOP:

-Better security
	-less attack surfaces
	-limited malware propogation
	-Better stability
	-Improves audit readiness
	
Implementing PLOP:

-ensure every accounts have only necessary privileges
	-start all accounts with minimal privileges
	-ensure seperation of privileges
	-use just in time privileges
	-make individual actions traceable
	-make audit privileges regular


## Subsection 5:

Why attackers target Industrial Control Systems:

-ICS is found everywhere nowadays for efficiency :)

motivation for attacking ICS:

-money,one way or other

How are ICS attacked:

-starts with  reconnaissance and survey of the environment getting a foothold in the network using various tactics
	complexity of launching an attack varies across different factors like security of the system to intended impact
	
Vulnerabilities exploited in an ICS:

 - *Policy and Procedure Vulnerabilities

    		Inadequate security architecture and design
    		Few or no security audits of the ICS environment
    		Inadequate security policies for the ICS
    		Lack of ICS specific configuration change management
    		No formal ICS security training and awareness program
    		Lack of administrative mechanisms for security enforcement
    		No ICS specific continuity of operations or disaster recovery plans
    		No specific or documented security procedures were developed from the security policies for the ICS environment

 - *Platform Configuration Vulnerabilities

	    Data unprotected on portable devices
	    Default system configurations are used
	    Critical configurations are not stored or backed up
	    OS and application security patches are not maintained
	    OS and application security patches are implemented without exhaustive testing
	    Inadequate access control policies such as ICS users have too many or two few privileges
	    OS and vendor software patches may not be developed until after security vulnerabilities are      discovered
	    Lack of adequate password policy, accidental password disclosures, no passwords used, default passwords used, or weak passwords used
	

 - *Platform Hardware Vulnerabilities

	    Inadequate testing of security changes
	    Lack of redundancy for critical components
	    Unsecure remote access of ICS components
	    Lack of backup power from generators or Uninterruptible Power Supply (UPS)
	    Dual network interface cards to connect networks
	    Inadequate physical protection of critical systems
	    Undocumented assets connected to the ICS network
	    Unauthorized personnel have physical access to equipment
	    Loss of environmental control could lead to overheating of a hardware
	    Radio frequency and electromagnetic pulses (EMP) cause disruptions and damage to circuitry

 - *Platform Software Vulnerabilities

	    Denial-of-Service (DoS) attack against ICS software
	    Intrusion detection/prevention software not installed
	    Installed security capabilities are not enabled by default
	    ICS software could be vulnerable to buffer overflow attacks
	    Mishandling of undefined, poorly defined, or “illegal” network packets
	    Unnecessary services are not disabled in the OS and could be exploited
	    No proper log management, which makes it difficult to trace security events
	    The OLE for Process Control (OPC) communications protocol is vulnerable to Remote Procedure Call (RPC) and Distributed Component Object Model (DCOM) vulnerabilities
	    Use of unsecure industry-wide ICS protocols such as DNP3, Modbus, and Profibus
	    Inadequate authentication and access control for configuration and programming software
	    Many ICS communications protocols transmit messages in clear text across the transmission media
	    ICS software and protocols’ technical documentation are easily available and can help adversaries plan successful attacks
    	    Logs and endpoint sensors are not monitored real-time and security breaches are not identified quickly

 - *Malware Protection Vulnerabilities

	    Anti-virus software not installed
    	    Anti-virus detection signatures not updated
    	    Anti-virus software installed in the ICS environment without exhaustive testing

 - *Network Configuration Vulnerabilities

	    Weak network security architecture
	    Passwords are not encrypted in transit
	    Network device configurations are not properly stored or backed up
	    Passwords are not changed regularly on network devices
	    Data flow controls e.g. Access Control Lists (ACL), are not used
	    Poorly configured network security devices e.g. incorrectly configured rules for firewalls, routers, etc.

 - *Network Hardware Vulnerabilities

	    Lack of redundancy for critical networks
	    Inadequate physical protection of network equipment
	    Loss of environmental control could lead to hardware overheating
	    Noncritical personnel have access to equipment and network connections
	    Unsecured USB and PS/2 ports that can be used to connect unauthorized thumb drives, keyloggers, etc.

 - *Network Perimeter Vulnerabilities

	    No network security perimeter defined
	    Firewalls are nonexistent or are incorrectly configured
        ICS control networks used for non-control traffic e.g. web browsing and email
        Control network services are not within the ICS control network e.g. DNS, DHCP are used by the control networks but are often installed in the corporate network

 - *Communication Vulnerabilities

	    Critical monitoring and control paths are not identified
	    Authentication of users, data, or devices is substandard or nonexistent
	    Many ICS communications protocols have no integrity checks built-in making it easy for adversaries to manipulate communications undetected
	    Standard, well-documented protocols are used in plain text e.g. sniffed Telnet, FTP traffic can be analyzed and decoded using protocol analyzers
	

 - *Wireless Connection Vulnerabilities

	    Inadequate authentication between clients and access points
	    Inadequate data protection between clients and access points

 - *Network Monitoring and Logging Vulnerabilities

	    No security monitoring of the ICS network
	    Inadequate firewall and router logs make it difficult to trace security events
	    possible-weaknesses-in-ICS-network

Industrial IOT and How it affects ICS:

-as ICS develops a lot of IOT devices are introduced to enhance productiveity IOT incorporates machine learning and big data analysis each device should be well protected for a secure system not investing in iot security lead to high scale vulnerabilities although hacking iot devices is hard the actors behind the procewss is knowledgabel and well skilld like us ifykyk misplaced devices are also a major security risk

## Subsection 6:

Physical Security For ICS/SCADA:

 - Importance:

	 -reduce the risk of loss or damage to the plant
	

 - sources of regulatory guidance:

	-NIST SP 800-53 Physical and Environmental Protection (PE)

 - Goals of physical security for ICS/SCADA:

	-preventing unauthorized access
		-preventing physical manipulaton like theft/destruction
		-Prevention of reconnassence
		-Prevention of introduction of unauthorized systems
		-prevention of introduction of unauthorized devices
		

 - Defence-in-depth:

	-attributes of defence-in-depth:
		-protection of physical locations:
		-protect using gates walls buildings etc
		-protection of sensitive it and information security assets:
		-locks on usb and cd ports and putting physical barriers

 - Access Control:

	-limiting access to importent personell only
		-People and asset tracking:
		-observing pople in close contact with the asset
		-securing devices in close contact with assets

 - FERC,NERC and CIP:

	-The Federal Energy Regulatory Commission, or FERC, is the federal body that has been granted authority over the power grid in the United States starting in 2005
		 -North American Electric Reliability Corporation, or NERC, is the nation’s electric reliability organization. 
		 NERC released Critical Infrastructure Protection (CIP) 014 standard for physical security

## Subsection 7:

Emerging Trends In OT Security:

 - AI/ML:

		    Artificial intelligence or Machine Learning can help improve OT security by:
		    Anomaly Detection: AI/ML algorithms are improving anomaly detection to identify irregular patterns in OT networks, signaling potential cyber threats.

		    Predictive Maintenance: AI/ML can predict maintenance needs in OT systems, enhancing efficiency and reducing downtime by foreseeing potential faults.

		    Behavioral Analysis: AI/ML tools analyze user and device behavior, identifying deviations from normal patterns and indicating potential security breaches.

		    Zero Trust Architecture: Integrating AI/ML in a zero-trust security model, where access is restricted and continuously verified regardless of location or network.

		    Autonomous Response: AI-driven systems can autonomously respond to security incidents in real-time, containing threats and minimizing damage.

		    AI-Powered Risk Assessment: AI/ML algorithms assess risk levels in OT environments, aiding in prioritizing security measures and resource allocation.

		    Secure Communication Enhancement: AI/ML can enhance secure communication protocols in OT, ensuring data integrity, confidentiality, and authentication.

		    Threat Intelligence Integration: AI/ML tools integrate threat intelligence to quickly identify and mitigate emerging threats based on current cyber threat landscapes.
	    

 - IoT:

		    Iot improves OT security By:
		    
		    -Edge Computing Security: As IoT devices increasingly process data at the edge, security measures are evolving to ensure that sensitive data is adequately protected at these decentralized   	
		    points, mitigating risks associated with data transmission to centralized servers.

    	    -Blockchain for IoT Security: Integrating blockchain technology to enhance the security of IoT devices by ensuring data integrity, authentication, and secure transactions. Blockchain can X	
    		 oints, mitigating risks associated with data transmission to centralized servers.

    		 -IoT Device Identity and Access Management (IAM): Implementing robust IAM solutions to control access to IoT devices, ensuring only authorized entities can interact with and manage these 
    		 devices. This includes multifactor authentication, biometrics, and secure credentials management.

    		 -Security-by-Design Principles: Integrating security measures from the inception of IoT device development and throughout the product lifecycle, focusing on building secure architectures, 
    		 encrypting communications, and adhering to recognized security standards.

   		    -AI-Driven IoT Security Analytics: Leveraging AI and machine learning to analyze vast amounts of IoT-generated data for detecting anomalies, predicting threats, and automating responses to 
   		    potential security incidents in real-time.

    		 -Quantum-Safe IoT Security: Preparing for the advent of quantum computing by implementing quantum-safe encryption algorithms to protect sensitive IoT data, ensuring security remains intact even 
    		 with the potential threat of quantum-based attacks.

    		 -IoT Security Standards and Regulations: Continued development and adoption of industry-specific IoT security standards and regulations to ensure a baseline of security across IoT deployments, 
    		 encouraging manufacturers and organizations to adhere to security best practices.

     		 -Supply Chain Security for IoT Devices: Strengthening security measures within the IoT device supply chain to prevent tampering, counterfeiting, or introduction of malicious components, ensuring 
    		 the integrity and security of IoT devices from manufacturing to deployment.

    		 -Secure Firmware and Patch Management: Ensuring the security of IoT devices through secure firmware development practices and efficient patch management strategies to address vulnerabilities 
    		 promptly and keep devices protected from emerging threats.

    		 -Privacy-Preserving IoT: Focusing on privacy-centric approaches to IoT data handling, such as differential privacy and federated learning, to enable valuable insights while protecting the 
    		 privacy of individuals and organizations.
    

 - Cloud:

    		-Cloud-Native Security Solutions: Developing and adopting security solutions specifically designed for cloud-native OT environments, addressing unique challenges like container security, 
    		serverless security, and microservices security.

    		-Zero Trust Architecture (ZTA): Implementing zero trust principles within the cloud, where no entity is inherently trusted, and strict identity verification and access controls are applied to 
    		all users and devices accessing OT systems hosted in the cloud.

    		-Secure Access Service Edge (SASE): Integrating SASE principles into OT security to secure access and data flows between cloud-based OT systems and end-users, ensuring consistent security 
    		policies and controls are applied irrespective of the location or device.

    		-Edge-Cloud Security Integration: Creating a secure integration between cloud infrastructure and edge devices, enabling real-time processing of data at the edge while ensuring secure 
    		communication and data transfer between the edge and cloud.

    		-Data Encryption and Privacy Enhancements: Enhancing encryption protocols and privacy measures for data in transit and at rest within the cloud, ensuring that sensitive OT data remains secure 
    		and private throughout its lifecycle.

    		-Security Automation and Orchestration: Leveraging automation and orchestration tools to manage security policies, incident response, and threat detection, allowing for quicker and more 
    		efficient responses to security incidents in the cloud.

    		-Cloud Workload Protection Platforms (CWPP): Implementing CWPP to secure cloud workloads, including OT applications and data, through real-time monitoring, vulnerability management, and threat 
    		detection.

    		-Threat Intelligence and Threat Hunting: Incorporating advanced threat intelligence and proactive threat hunting capabilities in the cloud to identify and mitigate potential threats targeting OT 
    		systems hosted in the cloud.

    		-Compliance and Regulatory Considerations: Ensuring OT systems hosted in the cloud comply with industry-specific regulations and standards, including data privacy laws and sector-specific 
    		compliance requirements related to critical infrastructure.
