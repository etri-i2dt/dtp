# 01 - Platforms

## Overview
This area represents the platform layer of DTP. It separates the main full-featured I2DT platform from an additional digital twin or sub-platform that connects through the local Ditto/DTT layer.

## Folder Structure

```text
01-platforms/
|-- main/
`-- sub/
```

## `main/`
The `main` folder is reserved for the main DTP implementation. The main platform is responsible for:

- DTD functions: digital twin data collection, storage, schema management, browsing, and monitoring;
- ISS functions: data transformation, API gateway behavior, routing rules, endpoint management, and transformation logs;
- connection to local Eclipse Ditto as the DTT middleware;
- message bus integration for real-time event delivery;
- dashboard integration for platform operation;
- AI/intelligence services for use-case-specific analytics.

When a Thing event is received from Ditto, the main platform should verify registration, retrieve complete data when needed, validate the schema, create or update data storage structures, and persist Thing attributes and properties.

## `sub/`
The `sub` folder is reserved for an additional digital twin or sub-platform. In the smart-parking use case, this sub-platform can generate or manage:

- vehicle entry and exit events;
- parking-slot occupancy status;
- vehicle location;
- zone and space occupancy;
- sensor status;
- parking facility operational data.

The sub-platform updates the corresponding Things in the local Ditto instance. The main platform then collects, stores, analyzes, and routes those updates.

## Federated Learning Role
The sub-platform and main platform may exchange model parameters, model updates, model outputs, or inference results. This enables the main DTP platform to aggregate, validate, and redistribute learned information across connected digital twins.
