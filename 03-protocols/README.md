---
title: Protocols
nav_order: 4
---

# 03 - Protocols

## Overview
This area documents protocols, message formats, and Thing model conventions used to connect sensors, simulators, sub-platforms, the local Ditto instance, and the main DTP services.

## Folder Structure

```text
03-protocols/
|-- messaging/
`-- model/
```

## `messaging/`
The `messaging` folder is reserved for protocol and message-bus documentation. DTP is designed to use:

- HTTP/REST for synchronous API calls and Ditto API integration;
- MQTT for sensor, simulator, and event-driven digital twin communication;
- WebSocket or server-sent events where live dashboard updates are required;
- a message bus layer for real-time event delivery between DTD, ISS, and intelligence services.

The local Ditto instance publishes Thing change events. DTP subscribes to or receives these events, validates the Thing data, stores it through the DTD subsystem, and can route transformed output through the ISS subsystem.

## `model/`
The `model` folder is reserved for Thing schema and model descriptions. A Thing represents a physical or simulated entity such as:

- facility;
- zone;
- parking space;
- vehicle;
- sensor;
- equipment;
- other mobility-related objects.

Each Thing should have an identifier, schema, attributes, and features. Schemas are used by DTD services to validate incoming data and by ISS services to transform data for external consumers.

## Protocol Responsibilities
- Local Ditto/DTT receives updates from sensors, simulators, and sub-platforms.
- Ditto emits events when a Thing state changes.
- DTP receives events over supported protocols.
- The DTD subsystem stores validated data.
- The ISS subsystem transforms and routes data to registered endpoints.
