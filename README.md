# WiFi-Based Intrusion Detection System for IoT Networks

A lightweight, passive, edge-based Intrusion Detection System (IDS) designed for WiFi-connected IoT networks using Raspberry Pi 5 and Suricata.

The system passively monitors WiFi traffic, detects common network reconnaissance activities using signature-based detection rules, records security events in structured JSON format, and processes relevant alerts through a Python-based alerting service.

---

## Project Overview

The increasing use of IoT devices has expanded the attack surface of wireless networks. Many small IoT environments do not use dedicated intrusion detection infrastructure because traditional enterprise security solutions can introduce additional cost, complexity, and hardware requirements.

This project explores a lightweight security monitoring approach that operates directly at the network edge.

The proposed system uses a Raspberry Pi 5 running Ubuntu 24.04 LTS together with Suricata as the intrusion detection engine. Network traffic is monitored passively through the WiFi interface, while Suricata analyzes packets using signature-based detection rules.

Detected security events are recorded in structured JSON logs and processed by a Python-based alerting service. High-severity events can generate summarized email notifications for the network administrator.

---

## Objectives

The main objectives of this project are:

- Design a lightweight IDS suitable for WiFi-based IoT networks.
- Monitor wireless network traffic passively.
- Detect common network reconnaissance activities.
- Use open-source security technologies.
- Process security alerts automatically.
- Reduce unnecessary notifications using severity and threshold-based filtering.
- Evaluate the feasibility of edge-based intrusion detection using Raspberry Pi.
- Provide a practical security monitoring solution for smaller IoT environments.

---

## System Architecture

```text
                         WiFi Network
                              │
                              ▼
                    ┌────────────────────┐
                    │    Raspberry Pi 5  │
                    │    Ubuntu 24.04    │
                    └─────────┬──────────┘
                              │
                              │ WiFi Traffic
                              ▼
                    ┌────────────────────┐
                    │     Suricata 8     │
                    │ Intrusion Detection│
                    │       Engine       │
                    └─────────┬──────────┘
                              │
                              │ Security Events
                              ▼
                    ┌────────────────────┐
                    │   JSON / Alert     │
                    │       Logs         │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │ Python Alerting    │
                    │      Service       │
                    └─────────┬──────────┘
                              │
                       Severity Filtering
                              │
                              ▼
                    ┌────────────────────┐
                    │ Email Notification │
                    │ Network Admin      │
                    └────────────────────┘
