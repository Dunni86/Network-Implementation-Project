# Network-Implementation-Project
A networking lab covering IP addressing, subnetting, and Cisco configuration.

# Cisco Packet Tracer Network Implementation Project

This project focuses on designing and configuring an enterprise network for **TechNova Limited** using Cisco Packet Tracer. The network connects the IT, Sales, and Human Resources (HR) departments, implements DHCP for IP address allocation, and uses Access Control Lists (ACLs) to restrict unauthorized access while permitting access to the HTTP server.

## Table of Contents

- [Project Overview](#project-overview)
- [Network Topology](#network-topology)
- [Tools and Technologies](#tools-and-technologies)
- [Configuration Steps](#configuration-steps)
- [Results and Findings](#results-and-findings)

## Project Overview

The purpose of this project is to design, implement, and test a secure enterprise network for TechNova Limited using Cisco Packet Tracer.

The project aims to achieve the following objectives:

- Design a network infrastructure connecting three departments: IT, Sales, and HR.
- Configure IP addressing for each department using separate subnets.
- Implement DHCP to provide IP address configuration to network devices.
- Configure routing to support communication between departments.
- Implement **Access Control Lists (ACLs)** to restrict Sales department access to IT workstations.
- Allow the Sales department to access the IT department's HTTP server while restricting unauthorized workstation access.
- Perform connectivity tests to verify network functionality and security policies.

## Network Topology

The network consists of a Cisco 2911 router, three Cisco 2960 switches, six PCs, and one server located in the IT department.

Each department operates within its own IP subnet, with the router providing network connectivity.

### Network Devices

- **1 Cisco 2911 Router:** Provides routing and DHCP services for the network.
- **3 Cisco 2960 Switches:** Connect devices within the IT, Sales, and HR departments.
- **6 PCs:** Two workstations assigned to each department.
- **1 Server:** Located in the IT department and configured to provide HTTP services.

### IP Addressing Scheme

| Department | Network Address   | Default Gateway | Number of PCs |
| ---------- | ----------------- | --------------- | ------------- |
| IT         | `192.168.10.0/24` | `192.168.10.1`  | 2             |
| Sales      | `192.168.20.0/24` | `192.168.20.1`  | 2             |
| HR         | `192.168.30.0/24` | `192.168.30.1`  | 2             |

**Subnet mask:** `255.255.255.0` (`/24`)

The IT department hosts the HTTP server. The router provides connectivity between the departmental networks, while ACL rules control access to IT workstations and the HTTP service.

## Tools and Technologies

- **Cisco Packet Tracer:** Network design, simulation, configuration, and testing.
- **Cisco 2911 Router:** Interdepartmental routing, DHCP services, and ACL implementation.
- **Cisco 2960 Switches:** Departmental network connectivity.
- **PC-PT End Devices:** Client workstations for the IT, Sales, and HR departments.
- **Server:** Hosts the HTTP service.
- **DHCP:** Automatically assigns IP configuration to client devices.
- **Access Control Lists (ACLs):** Enforces network access restrictions.
- **ICMP Ping:** Tests connectivity between network devices.
- **HTTP:** Tests permitted access to the server's web service.
- **Cisco IOS CLI:** Configures router services, routing, and access control rules.

## Configuration Steps

1. **Design the Network Topology**

   Open Cisco Packet Tracer and create the enterprise network by adding one Cisco 2911 router, three Cisco 2960 switches, six PCs, and one server. Arrange the devices to represent the IT, Sales, and HR departments.

2. **Connect the Network Devices**

   Connect the router to the departmental switches and connect each PC to its respective switch. Connect the server to the IT department's network.

3. **Configure the IP Addressing Scheme**

   Assign each department its own subnet and configure the router's departmental gateway addresses:

   - IT: `192.168.10.0/24`, gateway `192.168.10.1`
   - Sales: `192.168.20.0/24`, gateway `192.168.20.1`
   - HR: `192.168.30.0/24`, gateway `192.168.30.1`

4. **Configure DHCP Services**

   Configure DHCP on the router to provide IP address configuration to client devices in the departmental networks. Ensure that each DHCP configuration corresponds to the appropriate subnet and default gateway.

5. **Configure the End Devices**

   Set the PCs to obtain their IP addresses automatically through DHCP. Verify the assigned IP addresses and default gateways on representative PCs in the IT, Sales, and HR departments.

6. **Configure the HTTP Server**

   Set up the server in the IT department and enable its HTTP service. Verify that the server is reachable through its assigned IP address and that the HTTP service is available to permitted clients.

7. **Configure the Access Control List**

   Use the router's Cisco IOS CLI to implement an ACL that restricts access from the Sales department to IT workstations while allowing HTTP traffic to the IT server.

   The ACL should enforce the intended access policy without unnecessarily blocking permitted traffic. The exact ACL commands and interface placement should follow the router configuration used in the Packet Tracer project.

8. **Test Interdepartmental Connectivity**

   Use the `ping` command from the PCs to verify communication between departmental networks. The project screenshots document a successful ping from an HR PC to an IT PC and a failed ping from a Sales PC to an IT PC.

9. **Verify ACL Enforcement**

   Confirm that Sales workstations cannot access restricted IT workstations while permitted traffic remains available. Test access from a Sales PC to the HTTP server to verify that the server's web service remains accessible.

10. **Document the Results**

    Capture screenshots of the network topology, PC IP configurations, successful and failed ping tests, router ACL configuration, and successful HTTP access. Use these results to document the implementation and evaluate whether the network meets the intended connectivity and security requirements.

## Results and Findings

The project successfully demonstrates the implementation of a departmental enterprise network for TechNova Limited using Cisco Packet Tracer.

The documented results include:

- **Network implementation:** A network topology was designed using one Cisco 2911 router, three Cisco 2960 switches, six PCs, and one server.
- **Departmental segmentation:** The IT, Sales, and HR departments were assigned separate `/24` subnets.
- **DHCP configuration:** The router was configured to provide DHCP services for the departmental networks.
- **Successful connectivity test:** A ping from an HR PC to an IT PC succeeded, demonstrating connectivity between those endpoints.
- **Restricted connectivity:** A ping from a Sales PC to an IT PC failed, consistent with the intended restriction on Sales-to-IT workstation access.
- **ACL implementation:** An ACL was configured on the router to restrict Sales access to IT workstations while permitting HTTP access to the server.
- **HTTP service accessibility:** A Sales PC successfully accessed the HTTP server, demonstrating that the permitted web traffic was not blocked by the implemented policy.

The results indicate that the network configuration supports the intended balance between departmental connectivity and access control. The documented tests demonstrate both permitted and restricted communication paths.

## Author

**Name:** Ibidunni Dedewo
**Project:** Cisco Packet Tracer Network Implementation Project
**Date:** October 9, 2026
