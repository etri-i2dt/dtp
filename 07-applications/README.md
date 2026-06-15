---
title: Applications
nav_order: 8
---

# 07 - Applications

## Overview
This area is reserved for user-facing applications for DTP. The current folder structure separates DTD and ISS web interfaces.

## Folder Structure

```text
07-applications/
|-- dtd-web/
`-- iss-web/
```

## `dtd-web/`
The DTD web application is intended to support digital twin data management and monitoring workflows, including:

- Thing schema browsing and management;
- DTT/Ditto connection information;
- Thing data browsing and event history views;
- data table or storage status monitoring;
- platform operation dashboards for the DTD subsystem.

It consumes DTD APIs from [02-apis/dtd-api](../02-apis) and live updates from the platform event layer where available.

## `iss-web/`
The ISS web application is intended to support interoperability management workflows, including:

- transformation rule management;
- endpoint registration and status monitoring;
- routing rule management;
- transformation and delivery log browsing;
- dashboard views for data conversion status and system operation.

It consumes ISS APIs from [02-apis/iss-api](../02-apis) and can display operational data from the message bus, DTD subsystem, or monitoring services.

## AI and Intelligence Views
Dashboard functions may also expose outputs from the AI/intelligence layer, such as:

- current parking-space occupancy estimation;
- future occupancy prediction;
- anomaly alerts;
- parking status classification;
- routing or control recommendations.

## Related Areas
- [02-apis](../02-apis): backend API services.
- [03-protocols](../03-protocols): messaging and Thing model conventions.
- [06-security](../06-security): authentication, authorization, and dashboard security guidance.
- [08-deployments](../08-deployments): deployment structure.
