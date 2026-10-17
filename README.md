# CMPG 325 – MegaSave Network Design

## 📌 Project Overview

This repository contains the network design and implementation project for **CMPG 325 – Computer Networks (2026)** at **North-West University (NWU)**.

The project focuses on designing a reliable, scalable, and manageable computer network for **MegaSave Wholesale & Retail**, located in Klerksdorp. The network is designed to support current users while allowing for an expected **40% user growth within three years**.

## 🏢 Client Information

* **Client:** MegaSave Wholesale & Retail
* **Location:** Klerksdorp, South Africa
* **Industry:** Retail
* **Project:** CMPG 325 – Computer Networks
* **Project ID:** CMPG 325 – 2026 – 016
* **Client ID:** CLI-016
* **Student:** Tshireletso Dira
* **Student Number:** 45600244

## 🎯 Project Objectives

The main objectives of this project are to:

* Design a reliable computer network for MegaSave.
* Use the assigned IP address block `10.16.0.0/16`.
* Allow for 40% expected user growth within three years.
* Implement VLAN segmentation.
* Provide limited wireless access for cleaning and security contractors.
* Improve network management and troubleshooting.
* Support network fault isolation.
* Create and test the network topology using Cisco Packet Tracer.
* Document the network design and configuration.

## 🌐 Network Topology

The proposed physical topology is a **star topology**. A central router connects to switches, while the switches connect to the end devices.

The star topology was selected because it provides:

* Easy network management
* Easier troubleshooting and fault isolation
* Scalability for future expansion
* Support for wireless connectivity

Additional devices can be connected to available switch ports as the organisation grows.

## 🔌 Network Devices

The network consists of:

* Router
* Switch S1
* Switch S2
* Wireless Access Point (WAP)
* Staff PCs
* Contractor laptops
* Servers
* Internet connection

The router provides routing between different IP networks and acts as the default gateway for the network segments.

## 🏷️ VLAN Configuration

The network is divided into four VLANs:

| VLAN | Name       | Purpose                                           |
| ---- | ---------- | ------------------------------------------------- |
| 10   | Staff      | Regular MegaSave users                            |
| 20   | Management | Network and device management                     |
| 30   | Contractor | Wireless access for cleaning/security contractors |
| 40   | Servers    | Servers and central network services              |

VLAN segmentation separates different groups of users and devices into logical networks. This improves organisation, management, security, and troubleshooting.

## 🌍 IP Addressing

The assigned network address block is:

`10.16.0.0/16`

Variable Length Subnet Masking (VLSM) is used to allocate different subnet sizes according to the requirements of each VLAN. This helps reduce unnecessary IP address wastage and leaves address space available for future expansion.

### IP Addressing Plan

| VLAN            | Network         | Subnet Mask       | Gateway      | Address Assignment |
| --------------- | --------------- | ----------------- | ------------ | ------------------ |
| 10 – Staff      | `10.16.1.0/24`  | `255.255.255.0`   | `10.16.1.1`  | DHCP               |
| 20 – Management | `10.16.2.32/28` | `255.255.255.240` | `10.16.2.33` | Static             |
| 30 – Contractor | `10.16.2.0/27`  | `255.255.255.224` | `10.16.2.1`  | DHCP               |
| 40 – Servers    | `10.16.3.0/28`  | `255.255.255.240` | `10.16.3.1`  | Static             |

## 👥 Staff Network – VLAN 10

VLAN 10 is used for MegaSave's internal staff users.

* Network: `10.16.1.0/24`
* Gateway: `10.16.1.1`
* Address assignment: DHCP
* Host capacity: 254 usable addresses

DHCP automatically assigns IP addresses to staff computers, reducing the need for manual configuration.

## ⚙️ Management Network – VLAN 20

VLAN 20 is used for network infrastructure devices such as:

* Router
* Switches
* Wireless Access Point

The management network uses:

`10.16.2.32/28`

Network devices are assigned static IP addresses to make them predictable and easier for administrators to manage.

## 📶 Contractor Network – VLAN 30

VLAN 30 provides restricted wireless access to cleaning and security contractors working after hours.

* Network: `10.16.2.0/27`
* Gateway: `10.16.2.1`
* DHCP pool: `10.16.2.5 – 10.16.2.30`

Contractors are separated from the staff network using their own VLAN. This allows the network administrator to restrict contractor access to internal resources.

## 🖥️ Server Network – VLAN 40

VLAN 40 is dedicated to servers and central network services.

* Network: `10.16.3.0/28`
* Gateway: `10.16.3.1`
* Server 1: `10.16.3.2`
* Server 2: `10.16.3.3`

Servers use static IP addresses because they require stable and predictable addresses.

## 🔄 Inter-VLAN Communication

The router handles communication between the different VLANs.

For example, when a staff computer needs to communicate with a server, traffic follows this general path:

**Staff PC → Staff VLAN → Switch → Router → Server VLAN → Server**

The router also provides the connection between the internal MegaSave network and the Internet.

## 🛠️ Technologies Used

* Cisco Packet Tracer
* VLANs
* VLSM
* DHCP
* Static IP addressing
* Inter-VLAN routing
* Ethernet networking
* Wireless networking
* Network topology design

## 📁 Repository Contents

This repository will contain the project documentation, network diagrams, Cisco Packet Tracer files, configuration files, testing evidence, and other project deliverables.

As the project progresses through **Milestone 2 and the final submission**, additional configurations, testing evidence, and documentation will be added to the repository.

## 📈 Future Expansion

The network design provides room for future growth. The original `10.16.0.0/16` address block is larger than the initial requirements, allowing additional users, devices, and potentially more VLANs to be introduced as MegaSave expands.

## 📚 Project Status

### Milestone 1 – Client Design Review

* [x] Client requirements
* [x] Physical topology
* [x] Logical topology
* [x] VLAN design
* [x] IP addressing plan
* [x] Subnetting strategy
* [x] Initial GitHub repository

### Milestone 2

* [ ] Network configuration
* [ ] Cisco Packet Tracer implementation
* [ ] Testing
* [ ] Troubleshooting
* [ ] Configuration evidence

### Final Submission

* [ ] Final network implementation
* [ ] Final documentation
* [ ] Testing evidence
* [ ] Final project submission

## 👨‍💻 Author

**Tshireletso Dira**

North-West University
Department of Computer Science
CMPG 325 – Computer Networks
2026

## Milestone 2 - Client Implementation Review

### Client
**MegaSave Wholesale & Retail (Klerksdorp)**  
**Client ID:** CLI-016  
**Industry:** Retail  
**Addressing Block:** 10.16.0.0/16

### Network Design

The MegaSave network was implemented and simulated using Cisco Packet Tracer. The design uses an extended star topology, with switches providing central connectivity to end devices, servers and the wireless access point.

The network includes:

- Router R1
- Switches S1, S2 and S3
- Staff PCs
- Administration PC
- Servers
- Wireless Access Point (AP1)
- Contractor laptops

The topology was designed to provide structured connectivity and allow the network to accommodate the expected 40% user growth over three years.

### VLAN Implementation

The network was divided into VLANs to separate different groups of users and services:

| VLAN | Name | Purpose |
|---|---|---|
| 10 | Staff | Staff devices |
| 20 | Management | Management devices |
| 30 | Contractor | Contractor access |
| 40 | Servers | Server devices |

Trunk links were configured between the appropriate switches to carry the required VLAN traffic across the network.

### Client Change Request - CR14

The network accommodates the requirement that after-hours cleaning/security contractors require limited wireless access.

An access point was configured and connected to the switching infrastructure. Contractor laptops connect wirelessly through the access point and receive addressing from the network.

### Assigned Networking Challenge - Network Troubleshooting

The assigned networking challenge was **Network Troubleshooting (fault isolation scenario)**.

Troubleshooting involved verifying IP addressing, default gateways, DHCP operation, VLAN configuration, switch connectivity, trunk links and end-to-end communication.

The network was tested after troubleshooting to confirm successful connectivity.

### DHCP Verification

DHCP operation was verified using the router DHCP binding table. The bindings showed addresses assigned to devices in the configured network ranges, including:

- 10.16.1.2 – 10.16.1.11
- 10.16.2.5
- 10.16.2.7
- 10.16.2.9
- 10.16.2.34

This provided evidence that DHCP was successfully assigning addresses to network clients.

### Connectivity Testing

End-to-end connectivity was tested using the `ping` command.

Successful tests included communication between devices on different network segments and communication with the default gateway.

For example, PC7 successfully tested connectivity to the gateway:

```text
ping 10.16.1.1

Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

This confirms successful connectivity between the client device and its default gateway.

### Evidence

Milestone 2 evidence is included in this repository and contains screenshots showing:

- Network topology
- VLAN configuration
- Trunk configuration
- DHCP bindings
- Connectivity testing
- Troubleshooting evidence
- Final project verification

The final Cisco Packet Tracer implementation is also included in the repository.

### Milestone 2 Submission

The Milestone 2 submission includes:

1. **Working Packet Tracer file** – final `.pkt` implementation
2. **Assigned feature implemented** – Network Troubleshooting / fault isolation
3. **Testing evidence** – configuration and connectivity screenshots
4. **Updated GitHub portfolio** – project documentation and evidence

### Reflection

The implementation provided practical experience in designing, configuring and troubleshooting a simulated enterprise network. The troubleshooting process required verification of addressing, VLANs, trunk links, DHCP and end-to-end connectivity. Testing was performed after configuration changes to confirm that the final network was operational.

