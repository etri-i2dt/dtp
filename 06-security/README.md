# 06 - Security

## Overview
This area documents security requirements and practices for DTP. The platform handles digital twin data, endpoint routing, transformation rules, and operational logs, so authentication, authorization, transport security, and auditability are required across the full deployment.

## Security Scope
- Main DTP services, including DTD, ISS, dashboards, message bus, storage, and AI/intelligence services.
- Local Eclipse Ditto/DTT instance.
- Additional digital twin or sub-platform integrations.
- Sensors, simulators, and external systems connected through APIs or messaging protocols.

## Authentication
DTP deployments should define authentication for:

- dashboard users;
- API consumers;
- service-to-service calls;
- sensors, simulators, and sub-platforms;
- Ditto connections and policies.

Candidate mechanisms include JWT, OAuth 2.0, API keys for controlled service-to-service access, MQTT credentials, and X.509 certificates for device or broker authentication.

## Authorization
Recommended authorization controls include:

- role-based access control for platform users;
- endpoint-level API authorization;
- scope-based authorization for external integrations;
- Eclipse Ditto policies for Thing-level and feature-level permissions;
- least-privilege credentials for databases, message brokers, and service accounts.

Suggested roles:

- Administrator: full platform configuration and operation.
- Operator: monitoring and daily digital twin management.
- Viewer: read-only access to dashboards and data.
- Device or sub-platform: limited publish/update permissions.
- API consumer: limited data access or routing permissions.

## Transport and Network Security
- Use HTTPS for API and dashboard traffic.
- Use MQTT over TLS where MQTT is exposed outside a trusted network.
- Restrict broker topics by ACL.
- Use Kubernetes network policies or equivalent segmentation for deployed services.
- Do not expose storage services directly to public networks.
- Rate-limit public or partner-facing APIs.

## Data Security
- Encrypt sensitive data in transit.
- Encrypt backups and protect database credentials.
- Minimize personal or vehicle-identifying data where possible.
- Define data retention rules for event histories, logs, and monitoring data.
- Audit changes to schemas, routing rules, endpoints, and transformation rules.

## Component Checklist

### DTD subsystem
- Validate incoming Thing data against registered schemas.
- Log schema, table, and data-management changes.
- Restrict data browsing APIs by role and scope.

### ISS subsystem
- Validate transformation rules before activation.
- Restrict endpoint and routing rule management.
- Store transformation and delivery logs for audit and troubleshooting.
- Protect credentials used for external endpoints.

### Ditto/DTT layer
- Configure Ditto policies for Things and features.
- Authenticate connections from sensors, simulators, and DTP services.
- Use TLS for external Ditto gateway access.

### Message bus
- Require authentication for producers and consumers.
- Separate topics by environment and sensitivity.
- Restrict publish/subscribe permissions.

### Dashboards
- Enforce authenticated access.
- Apply secure cookie and session settings.
- Configure CORS and security headers.
- Avoid storing long-lived tokens in browser local storage.

## Threat Model
Primary threats to address:

- unauthorized access to digital twin data;
- malicious or malformed sensor and simulator payloads;
- interception of data in transit;
- injection attacks through schemas, transformation rules, or endpoint configuration;
- denial of service against APIs, brokers, or dashboards;
- leakage of endpoint credentials or database secrets;
- vulnerable third-party dependencies.

## Operational Practices
- Keep dependency and container image inventories current in [04-opensources](../04-opensources).
- Scan dependencies and container images before release.
- Store secrets outside source control.
- Use separate development, test, and production credentials.
- Enable centralized logs and monitoring.
- Define an incident response process before production deployment.
