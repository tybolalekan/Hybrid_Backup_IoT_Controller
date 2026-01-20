# Hybrid_Backup_IoT_Controller
A multi-interface, multi-network embedded IoT controller designed for intelligent inverters, variable frequency drives (VFDs), and LiFePO₄ battery systems. The system enables industrial communication, hybrid energy control, data logging, and remote monitoring across cellular, Wi-Fi, BLE, and LoRa networks.

---

## Project Overview

This project implements a **hybrid backup IoT controller** capable of integrating heterogeneous power devices using standard industrial communication interfaces.  
It is designed for **mission-critical and off-grid power systems**, providing reliability, redundancy, and intelligent energy prioritization even during power or network outages.

The controller combines **deterministic real-time control** with **cloud-connected IoT capabilities**, making it suitable for smart energy systems, microgrids, telecom backup power, and industrial automation.

---

## System Architecture

### High-Level Architecture

```
+-----------------------------+
|   Inverters / VFDs / BMS    |
| (RS232 / RS485 / CAN BUS)   |
+-------------+---------------+
              |
              v
+-----------------------------------+
|        STM32F407 MCU               |
| - Protocol Handling                |
| - Control Logic                    |
| - Energy Priority Decisions        |
| - Data Aggregation                 |
+-----------------------------------+
     |              |              |
     |              |              |
     v              v              v
+-----------+  +-------------+  +----------------+
| MicroSD   |  | RTC Module  |  | Dry Contacts   |
| 64GB      |  | Time Backup |  | Energy Control |
+-----------+  +-------------+  +----------------+

     |
     v
+---------------------------------------------+
| Communication & Connectivity Layer           |
|                                             |
| - SIMCOM A7670E (4G LTE, Dual SIM)           |
| - Heltec WiFi + BLE 5.0 + LoRa Module        |
+---------------------------------------------+

     |
     v
+---------------------------------------------+
| Cloud / Server / Monitoring Dashboard        |
| - Telemetry                                 |
| - Logs                                     |
| - Alerts                                   |
| - Remote Configuration                     |
+---------------------------------------------+
```

### Architectural Highlights
- MCU-centric design for **real-time deterministic control**
- **Multi-radio redundancy** (LTE, Wi-Fi, LoRa)
- **Offline-first operation** with SD card logging
- Physical **dry contact control** for energy prioritization

---

## Hardware Components

### Controllers & Communication Modems
- **STM32F407** – Main real-time controller and protocol processor  
- **Heltec WiFi + LoRa module** – Wi-Fi, BLE 5.0, and LoRa connectivity  
- **SIMCOM A7670E** – 4G LTE modem with dual SIM support  

---

## Communication Interfaces

- **4 × RS232** – Inverter, VFD, and battery communication  
- **2 × CAN** – High-reliability industrial networking  
- **1 × RS485 (4 channels)** – Multi-drop industrial device support  
- **USB-C** – Configuration, debugging, and firmware updates  

---

## Connectivity

- **4G LTE** with **Dual SIM failover**
- **Wi-Fi** for LAN-based monitoring and configuration
- **Bluetooth Low Energy (BLE 5.0)** for provisioning and maintenance
- **LoRa** for long-range, low-power telemetry

---

## Control & Automation

- **Dry contact outputs** for:
  - Energy source prioritization
  - Automated switching between grid, inverter, and battery
- Supports hybrid power logic for improved uptime and efficiency

---

## Storage & Reliability

- **MicroSD card (up to 64GB)** for:
  - Telemetry data
  - Event logs
  - Diagnostics
- **RTC with backup** ensures accurate timestamping during power outages

---

## Key Features

- Multi-protocol industrial communication
- Hybrid energy system control
- Remote monitoring and telemetry
- Offline data logging with time backup
- Redundant network connectivity
- Vendor-agnostic power system integration

---

## Use Cases

- Hybrid inverter and battery backup systems  
- Industrial VFD monitoring and control  
- Microgrids and smart energy deployments  
- Telecom and critical infrastructure power backup  
- Remote and off-grid installations  

---

## Author

**Toyyib Olalekan Akinkunmi**  
Embedded Systems & IoT Engineer  

---

## License

This project is proprietary / for portfolio demonstration purposes.
