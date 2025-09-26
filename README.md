# FireWall / VLAN Setup

## Hardware
![Network Hardware](/Images/NetworkHardware.jpg "Network Hardware") <br>
- Modem - xFI Gateway <br>
- Firewall/Router - Protectli Vault FW4B <br>
- Switch - TP-Link TL-SG108E <br>
- Access Point - TP-Link AX1800 <br>

## Installation and Configuration

### Router/ Firewall Installation and Configuration
- Installed PfSense onto dedicated Router/Firewall device 

![Installing PfSense](/Images/installpfsense.jpg "Installing PfSense") <br>
- Set up residential gateway device given by ISP to act as just a modem in my network.(Bridge Mode)<br>
- Created VLAN Interfaces in PfSense <br>
- Configured firewall rules to allow main LAN traffic to flow through all VLANs but blocked VLAN traffic from accessing each other and the main LAN<br>
- Configured DHCP servers on each VLAN to use google DNS<br>
- Set up static IPs on LAN for Access Point and Switch

### Switch and Access point Configuration
- Configured ports on switch to allow traffic from the correct VLANs to flow through designated ports

![Installing PfSense](/Images/switchconfig.jpg "Installing PfSense") <br>
- Set AP to multi-SSID Mode

![Installing PfSense](/Images/multissid.jpg "Installing PfSense") <br>
- Created SSIDs for VLANs

## Network Design & Segmentation
![Installing PfSense](/Images/VLANs.jpg "Installing PfSense") <br>
I seperated my network into 5 VLANs with LAN, Guests, and IoT Devices being the main VLANs. There are 2 more one for my devices and one for my brother these two were mainly for experimentation and practice. These VLANs were created to segment and isolate devices to improve performance, limit attack surface, and seperate traffic. Performance is improved by reducing broadcast domains and QoS can be enabled to prioritize important traffic. Attack surface is reduced by seperating critcal devices from less secure devices such as servers(critical) and IoT devices (less secure). Traffic can be seperated depending on function, compliance, and as said before for security reasons.
