# DTP (Digital Twin Platform)

## Overview
DTP is ETRI's Digital Twin Platform for smart mobility use cases. It is an I2DT platform that manages digital twin objects, collects real-time Thing data, stores and validates schema-based data, supports interoperability between heterogeneous digital twins, and provides dashboard and API functions for monitoring and data access.

![DTP smart parking integrated platform concept](images/concept.png)

## Documentation

<div class="grid cards" markdown>

-   :material-server-network: __Platforms__

    ---

    Main DTP platform and sub-platform structure.

    [:octicons-arrow-right-24: Explore](01-platforms/README.md)

-   :material-api: __APIs__

    ---

    DTD and ISS API areas.

    [:octicons-arrow-right-24: Explore](02-apis/README.md)

-   :material-swap-horizontal: __Protocols__

    ---

    Messaging protocols and Thing model conventions.

    [:octicons-arrow-right-24: Explore](03-protocols/README.md)

-   :material-package-variant: __Open Sources__

    ---

    Open-source component and license inventory.

    [:octicons-arrow-right-24: Explore](04-opensources/README.md)

-   :material-test-tube: __Simulations__

    ---

    Simulation and test-data generation areas.

    [:octicons-arrow-right-24: Explore](05-simulations/README.md)

-   :material-shield-lock: __Security__

    ---

    Security requirements, threat model, and guidance.

    [:octicons-arrow-right-24: Explore](06-security/README.md)

-   :material-application-brackets: __Applications__

    ---

    DTD and ISS web application areas.

    [:octicons-arrow-right-24: Explore](07-applications/README.md)

-   :material-rocket-launch: __Deployments__

    ---

    Deployment structure for broker, Ditto, and more.

    [:octicons-arrow-right-24: Explore](08-deployments/README.md)

</div>

## Architecture
DTP is designed around three cooperating parts:

1. Main I2DT solution
    - Digital Twin Data (DTD) subsystem for Thing data collection, storage, schema management, data browsing, and monitoring.
    - Interoperability Support System (ISS) subsystem for data transformation, API gateway functions, routing rules, endpoint management, and transformation logs.
    - Local Ditto/DTT connection layer for receiving Thing events.
    - Message bus for real-time event delivery between DTD and ISS services.
    - Dashboard layer for monitoring endpoints, transformation rules, data conversion status, and system operation.
    - AI/intelligence layer for use-case-specific analysis.

2. Local Eclipse Ditto instance
    - Acts as the local DTT middleware.
    - Manages Things representing facilities, zones, parking spaces, vehicles, sensors, equipment, and other mobility objects.
    - Publishes events when Thing state changes.
    - Connects to DTP through supported protocols such as HTTP, MQTT, or WebSocket.

3. Additional digital twin / sub-platform
    - Generates, manages, or simulates parking-related data.
    - Updates Things in the local Ditto instance.
    - May exchange model outputs or federated-learning updates with the main platform.

## Inputs
- Real-time digital twin events from the local Ditto/DTT instance.
- Thing schemas, attributes, features, and metadata.
- Data transformation rules between source and target schemas.
- Endpoint and routing information for connected digital twins or external services.

## Outputs
- Stored and managed digital twin data.
- Validated Thing attributes, features, and event histories.
- Transformed data for connected digital twins or external systems.
- API responses for data browsing, schema management, and monitoring.
- Dashboard visualizations of digital twin status, transformation rules, endpoints, and system operation.
- Logs for transformation, routing, endpoint communication, and system monitoring.

## Prototype Use Flow
1. Deploy DTP components: DTD subsystem, ISS subsystem, dashboard services, message bus, database services, and AI/intelligence service.
2. Deploy and configure the local Eclipse Ditto instance.
3. Register Thing schemas for the target use case, such as parking spaces, vehicles, sensors, zones, facilities, or equipment.
4. Connect physical sensors, simulators, or a sub-platform to Ditto.
5. Register the required DTT/Ditto connection information in DTP.
6. Configure ISS transformation rules by defining mappings between source and target schemas.
7. Register API endpoints and routing rules for connected digital twins, sub-platforms, or external services.
8. Start data generation or collection from the sub-platform, sensor, or simulator layer.
9. Monitor Thing events, stored data, transformation results, endpoint status, and logs through the dashboard.
10. Run the AI/intelligence service to analyze live and historical data.

## Smart Parking Use Case
The reference use case is smart parking. The platform can support:

- parking-space occupancy estimation;
- future occupancy prediction;
- anomaly detection in incoming data;
- parking status classification;
- intelligent recommendations for routing or control;
- exchange of raw data, transformed data, inference results, model outputs, or federated-learning updates between connected digital twins.

## Tool Information
- Version: 0.1, prototype version.
- Type: Closed source.
- Source code (authorized access only): [github.com/etri-i2dt/dtp-src](https://github.com/etri-i2dt/dtp-src)
- DTD Web (deployed at ETRI server): [dtd-dashboard.129.254.222.205.nip.io:20080](http://dtd-dashboard.129.254.222.205.nip.io:20080/)
- ISS Web (deployed at ETRI server): [issui.129.254.222.213.nip.io:20080](http://issui.129.254.222.213.nip.io:20080/)
- For source code requests or platform access, contact Yangkoo Lee (yk_lee[at]etri.re.kr) or Jiwoo Han (chau[at]etri.re.kr).

## Acknowledgement
This research was financially supported by the Ministry of Trade, Industry and Energy (MOTIE) and Korea Institute for Advancement of Technology (KIAT) through the International Cooperative R&D program (P0027981 — Intelligent Interoperable Digital Twins (I2DT)).

