# Nmap-Local-Network-Port-Scanning

## Objective
The objective is to identify active devices and open ports within a local network through the utilization of Nmap, thereby gaining an understanding of the fundamental exposure of network services.

## Tools Used

- Nmap 7.991
- Npcap 1.89
- Windows Command Prompt
- Wireshark (optional)

## Methodology
-Nmap and Npcap were installed.
-The local IPv4 network range was identified.
-A TCP SYN scan was conducted using Nmap.
-Discovered hosts and open ports were documented.
-The services associated with the discovered ports were researched.
-The security implications of the exposed services were considered.
-The scan results were saved.

## Command Used
-ipconfig
-nmap -sn 192.168.1.0/24
-nmap -sS 192.168.1.0/24
-nmap -sS 192.168.29.0/24 -oN scan_results.txt

## Network Information

Local IP: 192.168.29.xxx
Network range: 192.168.29.0/24

## Results

Nmap host discovery identified 4 active devices on the local network.

The TCP SYN scan saved in scan_results.txt identified 3 responding hosts and their open TCP ports.

## Active Hosts Found During Host Discovery
IP Address	Vendor            Device Information	Status

-192.168.29.1	                Servercom (India) Private Limited	Up
-192.168.29.144	              Unknown	Up
-192.168.29.168	              Samsung Electronics	Up
-192.168.29.xxx	               Local Windows PC	Up

## Security Observations
The scan revealed that various devices within the local network expose distinct TCP services. The gateway was found to expose DNS, HTTP/HTTPS, and UPnP-related services. While these services may be essential for standard router operations, it is advisable to disable or restrict non-essential services as appropriate. An unidentified device was observed to expose two TCP ports; however, due to the lack of identification of the device and its specific applications, further investigation is necessary before making any security assessments. The Windows computer exposed ports typically associated with Windows RPC, NetBIOS, and SMB. It is crucial that these services are adequately protected by the Windows Firewall and are not unnecessarily exposed to untrusted networks. It is important to note that an open port does not inherently indicate a device's vulnerability. The security risk is contingent upon factors such as the service, configuration, authentication, software version, and network accessibility.

## What I Learned
-Methods for identifying a local IPv4 network range
-Techniques for host discovery utilizing Nmap
-TCP SYN scanning procedures
-Methods for identifying active devices
-Techniques for identifying open and closed TCP ports
-Understanding of common network services
-Fundamentals of basic network reconnaissance
-Comprehension of network service exposure
-Basic concepts of network security and firewalls

## Interview Questions
1. What is an open port?

An open port is a network port on which a service is actively listening for incoming connections.

2. How does Nmap perform a TCP SYN scan?

A TCP SYN scan sends a SYN packet to a target port. If the target responds with SYN-ACK, Nmap considers the port open. Nmap can then send a RST packet to terminate the connection without completing the normal TCP connection.

3. What risks are associated with open ports?

Open ports can expose network services to other devices. If a service is unnecessary, poorly configured, outdated or vulnerable, it may increase the attack surface of the device.

4. What is the difference between TCP and UDP scanning?

TCP is connection-oriented and uses mechanisms such as SYN, SYN-ACK and ACK. UDP is connectionless and does not establish a traditional TCP-style connection. Nmap therefore uses different techniques to determine the state of TCP and UDP ports.

5. How can open ports be secured?

Unnecessary services can be disabled, firewall rules can restrict access, software can be updated, authentication can be strengthened, and services can be exposed only to trusted networks when required.

6. What is the role of a firewall?

A firewall controls network traffic according to configured rules. It can allow required connections and block unauthorized or unnecessary network access.

7. What is port scanning and why is it performed?

Port scanning is the process of checking network ports on a host to determine their states and identify potentially available services. It can be used for legitimate network administration, troubleshooting, security assessments and authorized penetration testing.

8. How does Wireshark complement port scanning?

Nmap identifies hosts and ports, while Wireshark can capture and analyze the network packets involved in communication. This can help understand protocols, packet exchanges and network behavior in greater detail.
