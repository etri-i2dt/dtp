# 02 - APIs

## Overview
This area is reserved for API services used by DTP. The APIs are split into DTD services for digital twin data management and ISS services for interoperability and routing.

## Folder Structure

```text
02-apis/
|-- dtd-api/
`-- iss-api/
```

## `dtd-api/`
The DTD API area covers digital twin data services. It is expected to provide API functions for:

- Thing schema registration and management;
- Thing attribute, feature, and metadata management;
- digital twin data ingestion from Ditto/DTT events;
- validation of incoming Thing data against registered schemas;
- storage and retrieval of current and historical digital twin data;
- data browsing and monitoring support for dashboards.

Typical API consumers include the DTD web application, DTT/Ditto connection services, AI/intelligence services, and external systems that need validated digital twin data.

## `iss-api/`
The ISS API area covers interoperability services. It is expected to provide API functions for:

- source and target schema mapping;
- data transformation rule management;
- endpoint registration and management;
- routing rule configuration;
- API gateway and forwarding behavior;
- transformation, routing, and endpoint communication logs.

The ISS API transforms DTP-managed data into formats required by connected digital twins, sub-platforms, or external services.

## API Inputs
- Real-time Thing events and stored digital twin data.
- Thing schemas, attributes, features, and metadata.
- Transformation rules between heterogeneous schemas.
- Endpoint and routing configuration.

## API Outputs
- Validated data records and event histories.
- Transformed payloads for connected systems.
- API responses for browsing, schema management, monitoring, and interoperability.
- Operational logs for transformation, routing, and endpoint communication.
