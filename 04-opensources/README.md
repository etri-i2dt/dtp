---
title: Open Sources
nav_order: 5
---

# 04 - Open Sources

## Overview
This area documents open-source software expected to be used by DTP and related deployment environments. It is intended as a license and dependency inventory for the prototype.

## Core Components

| Component | Purpose | License / Notes |
| --- | --- | --- |
| Eclipse Ditto | Local digital twin middleware / DTT layer for Thing management and event publication | Eclipse Public License 2.0 |
| Docker | Container packaging and local execution | Apache License 2.0 |
| Kubernetes | Container orchestration for deployed services | Apache License 2.0 |
| MQTT broker, such as Eclipse Mosquitto | Publish/subscribe communication for sensors, simulators, and event streams | Eclipse Public License 2.0 |
| PostgreSQL | Relational storage for platform data | PostgreSQL License |
| MongoDB | Common backing store option for Eclipse Ditto deployments | Server Side Public License or vendor-specific terms depending on distribution |
| Kafka or equivalent message broker | Real-time event delivery between DTD, ISS, and other services | Apache License 2.0 |

## Application and API Technologies

| Component | Purpose | License / Notes |
| --- | --- | --- |
| Spring Boot / Java ecosystem | Candidate backend API implementation for DTD and ISS services | Apache License 2.0 |
| Next.js / React | Candidate dashboard implementation for DTD and ISS web interfaces | MIT |
| FastAPI / Python ecosystem | Candidate implementation for AI, event detection, or integration services | MIT / BSD-style licenses by package |
| Node-RED | Simulation and flow-based data generation for prototype testing | Apache License 2.0 |

## AI and Analytics
The AI/intelligence layer may use additional open-source libraries for:

- occupancy estimation;
- future occupancy prediction;
- anomaly detection;
- parking status classification;
- routing or control recommendations;
- federated-learning model exchange.

Specific ML libraries should be documented here when selected for implementation.

## License Compliance
When adding or updating a component:

1. Record the component name, version, license, and purpose.
2. Keep third-party license notices with redistributions.
3. Preserve copyright notices.
4. Review obligations for copyleft or source-available licenses.
5. Check compatibility with the closed-source distribution model.

## Related Folders
- [08-deployments](../08-deployments): deployment structure for Ditto, broker, storage, monitoring, and platform services.
- [06-security](../06-security): dependency security and operational security guidance.
