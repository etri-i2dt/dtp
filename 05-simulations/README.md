---
title: Simulations
nav_order: 6
permalink: /05-simulations/
---

# 05 - Simulations

## Overview
This area is reserved for simulators and test-data generators used to exercise the DTP prototype without requiring all physical devices to be present.

## Folder Structure

```text
05-simulations/
|-- carla/
`-- node-red/
```

## `node-red/`
The `node-red` folder is reserved for flow-based simulation and data generation. In the smart-parking use case, Node-RED flows can be used to:

- register sample Things in Eclipse Ditto;
- update Thing attributes and features;
- generate vehicle entry and exit events;
- generate parking-slot occupancy changes;
- simulate sensor status and operational telemetry.

Generated updates should be sent to the local Ditto instance. DTP then receives the resulting Thing events through the Ditto/DTT connection layer.

## `carla/`
The `carla` folder is reserved for CARLA-based mobility simulation. Potential uses include:

- vehicle movement simulation;
- traffic scenario generation;
- synthetic sensor data generation;
- validation of routing, occupancy, and control recommendations.

## Integration Flow
1. A simulator or test-data generator creates parking or mobility data.
2. The simulator updates a corresponding Thing in the local Ditto instance.
3. Ditto publishes the Thing event.
4. DTP validates and stores the event through the DTD subsystem.
5. The AI/intelligence layer analyzes the data.
6. The ISS subsystem transforms and routes output to connected systems.
