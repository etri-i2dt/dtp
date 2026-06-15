---
title: Deployments
nav_order: 9
---

# 08 - Deployments

## Overview
This area is reserved for deployment assets for the DTP prototype and its supporting infrastructure.

## Folder Structure

```text
08-deployments/
|-- broker/
|-- ditto/
|-- monitoring/
|-- others/
|-- platform/
`-- storage/
```

## `broker/`
Reserved for message broker deployment files. The broker layer delivers real-time events between:

- Ditto/DTT connection services;
- DTD data services;
- ISS transformation and routing services;
- AI/intelligence services;
- dashboards or monitoring services where live updates are required.

Kafka, MQTT brokers, or equivalent messaging infrastructure can be deployed here depending on the target environment.

## `ditto/`
Reserved for local Eclipse Ditto deployment files. Ditto acts as the DTT layer and manages Things for physical or simulated mobility entities.

Ditto responsibilities:

- Thing registration and management;
- current digital twin state representation;
- sensor, simulator, and sub-platform update reception;
- event publication on Thing state changes;
- integration with DTP through HTTP, MQTT, WebSocket, or supported connectors.

## `platform/`
Reserved for main DTP service deployments, including:

- DTD subsystem services;
- ISS subsystem services;
- DTT/Ditto connection services;
- dashboards;
- AI/intelligence services;
- API gateway or ingress resources.

## `storage/`
Reserved for database and persistence deployment files. Storage may include:

- digital twin schemas;
- Thing attributes, features, and histories;
- transformation rules;
- endpoint and routing configuration;
- transformation and system logs;
- AI/intelligence outputs or model metadata.

## `monitoring/`
Reserved for observability deployments such as metrics, logs, dashboards, and alerting. Monitoring should cover:

- API health;
- broker health;
- Ditto/DTT connectivity;
- data ingestion status;
- transformation success and failure rates;
- endpoint communication status;
- storage and system resource usage.

## `others/`
Reserved for supporting deployment files that do not fit the primary categories.

## Deployment Sequence
1. Deploy storage services.
2. Deploy message broker services.
3. Deploy the local Ditto instance.
4. Deploy main DTP platform services.
5. Deploy dashboards and ingress/API gateway resources.
6. Deploy monitoring and logging.
7. Register schemas, endpoints, routing rules, and Ditto connection information.
8. Start simulators, sensors, or sub-platform integrations.
