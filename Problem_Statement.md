### Problem

Modern hybrid power systems often integrate inverters, VFDs, and battery management systems from different vendors, each using different communication standards. Existing solutions lack **resilience**, **remote visibility**, and **intelligent energy prioritization**, especially in unreliable power and network environments.

### Solution

I designed and implemented a **hybrid embedded IoT controller** that unifies industrial communication, real-time control, and cloud connectivity into a single platform. The system leverages an **STM32F407 MCU** to handle deterministic control tasks while integrating cellular and low-power wireless technologies for remote access.

### Implementation

The controller interfaces with power devices using **RS232, RS485, and CAN buses**, aggregating telemetry and executing control logic locally. A **SIMCOM A7670E LTE modem** provides wide-area connectivity with **dual SIM redundancy**, while a **Heltec WiFi + LoRa module** enables local access, BLE-based provisioning, and long-range telemetry.

To ensure reliability, all operational data is stored locally on a **64GB microSD card**, with an **RTC-backed timekeeping system** maintaining accurate logs during outages. **Dry contact outputs** are used to enforce energy priority rules, allowing automatic switching between power sources.

### Outcome

The resulting system is a **resilient, scalable, and vendor-agnostic hybrid power controller** capable of operating both online and offline. It significantly improves system observability, uptime, and automation, making it suitable for industrial, energy, and critical infrastructure deployments.
