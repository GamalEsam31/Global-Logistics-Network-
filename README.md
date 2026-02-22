# Global-Logistics-Network-
Global Logistics Network (GLN) is a comprehensive enterprise network design for a hypothetical global logistics company, featuring five sites: Headquarters, three branches, and a Data Center. The project implements VLAN segmentation, EIGRP dynamic routing, DHCP for IP assignment, and centralized DNS using Cisco technologies in Packet Tracer.

# Global Logistics Network (GLN) Project

This repository contains the design, implementation, and documentation for the GLN enterprise network, a graduation project simulating a global logistics company's network using Cisco technologies.

## Project Structure
- **docs/**: Full project report and details.
- **configs/**: Configuration scripts for routers and switches.
- **diagrams/**: Network topology diagrams (add your images here).
- **tests/**: Verification outputs and tests.

## Executive Summary
The GLN network is a comprehensive enterprise network design for a global logistics company comprising five sites (Headquarters + 3 Branches + Data Center).  
The objective: Provide secure and fast connectivity between sites, segment the network with VLANs for each department, automatically assign IP addresses via DHCP, and a centralized DNS service.  
Cisco technologies (ROAS, EIGRP, Trunking, DHCP, Password Encryption) were used, achieving full connectivity between all devices in the network.

## How to Simulate
- Use Cisco Packet Tracer to build the topology.
- Apply configurations from the `configs/` folder.
- Test connectivity as described in the report.

For full details, see `docs/Project-Report.md`.

# Project Report: Design and Implementation of the Global Logistics Network (GLN)

## Cover Page
- Project Title: Design and Implementation of the Global Logistics Network (GLN)  
- Student Name: Gamal  
- College – Department – Year: [Your Info]  
- Supervisor: [Supervisor Name]  
- Date: February 2026

## Table of Contents
- Introduction  
- Requirements Analysis  
- Network Design (Topology)  
- Implementation Details (Configuration)  
- Verification and Testing  
- Results and Challenges  
- Conclusion and Recommendations  
- References

## Introduction
Global Logistics Network (GLN) is a hypothetical global logistics company with a headquarters, 3 branches, and a data center. The network supports daily operations like goods transportation, inventory management, and inter-branch communication.  

Main Objectives:  
1. Full connectivity between sites.  
2. Secure segmentation for departments.  
3. Automatic IP management.  
4. Internal DNS service.  
5. Access security.

## Requirements Analysis
- 5 Sites.  
- 5 Routers + 5 Switches.  
- VLANs for each department in every site.  
- WAN between HQ and branches/data center.  
- EIGRP for dynamic routing.  
- DHCP for each VLAN.  
- Centralized DNS in the data center (www.gln.com → 192.168.90.10).  
- Passwords + Encryption + Warning Banner.

## Network Design (Topology & Addressing)

| Site          | Router         | Switch         | VLAN 1 (ID/Name/Network)        | VLAN 2 (ID/Name/Network)        | WAN Link (Subnet)            | Router IP on WAN |
|---------------|----------------|----------------|---------------------------------|---------------------------------|------------------------------|------------------|
| Headquarters | R1-HQ         | SW1-HQ        | 10/Admin/192.168.10.0/24       | 20/Finance/192.168.20.0/24     | - (Central)                 | -                |
| Branch 1     | R2-Branch1    | SW2-Branch1   | 30/Sales/192.168.30.0/24       | 40/HR/192.168.40.0/24          | 10.0.0.0/30                 | 10.0.0.2         |
| Branch 2     | R3-Branch2    | SW3-Branch2   | 50/Marketing/192.168.50.0/24   | 60/Dev/192.168.60.0/24         | 10.0.4.0/30                 | 10.0.4.2         |
| Branch 3     | R4-Branch3    | SW4-Branch3   | 70/Inventory/192.168.70.0/24   | 80/Shipping/192.168.80.0/24    | 10.0.8.0/30                 | 10.0.8.2         |
| Data Center  | R5-DC         | SW5-DC        | 90/Server/192.168.90.0/24      | 100/Backup/192.168.100.0/24    | 10.0.12.0/30                | 10.0.12.2        |

Topology: HQ as central hub with serial WAN links to branches and DC. Use tools like Draw.io for diagrams.

## Implementation (Configuration Scripts)
See `configs/` for full scripts. Example for R1-HQ:


DNS Server: Static IP 192.168.90.10, A Record for www.gln.com.

## Verification and Testing
- Ping across sites.  
- `show ip route`, `show ip eigrp neighbors`.  
- `show vlan brief`, `nslookup www.gln.com`.  
- `show ip dhcp binding`.

## Conclusion
The project achieved a secure, scalable network for logistics operations. Challenges: Clock rate setup and sub-interfaces, resolved successfully.

## Recommendations
- Add VPN.  
- ACLs for traffic control.  
- Redundancy with OSPF.

## References
- Cisco Networking Academy.  
- Packet Tracer Docs.  
- Cisco EIGRP Guides.
