# FNM Architecture

## High-Level Design

Finmech Network Monitor (FNM) separates presentation, API, persistence, and monitoring responsibilities.

```text
Users
  |
  v
Next.js Dashboard
  |
  | REST
  v
FastAPI Backend
  |            \
  v             v
PostgreSQL    Monitoring Engine
                 |
                 +-- ICMP
                 +-- SNMP
                 +-- Interface State
                 |
                 v
             Network Devices
```

## Components

### Frontend
The Next.js interface presents device state, health summaries, alerts, and monitoring information.

### API
FastAPI provides application and monitoring endpoints consumed by the frontend.

### Monitoring Engine
The polling layer evaluates reachability and telemetry and feeds state transitions into the alerting workflow.

### Database
PostgreSQL stores application state, monitored-device information, and alert lifecycle data.

## Alert State Model

```text
HEALTHY
   |
failure detected
   v
ACTIVE -----> ACKNOWLEDGED
   |               |
   +-------+-------+
           |
       recovery
           v
       RECOVERED
```

Repeated failures should not create duplicate open incidents for the same monitored condition.

## Public Documentation Boundary

Examples in this document are intentionally generic. Internal addresses, production topology, credentials, organization-specific configuration, and private operational data are excluded.
