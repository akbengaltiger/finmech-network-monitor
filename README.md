# Finmech Network Monitor (FNM)

> A custom network monitoring platform focused on device visibility, availability monitoring, alert lifecycle management, and infrastructure observability.

![Status](https://img.shields.io/badge/status-active%20development-success)
![Backend](https://img.shields.io/badge/backend-FastAPI-009688?logo=fastapi)
![Frontend](https://img.shields.io/badge/frontend-Next.js-black?logo=nextdotjs)
![Database](https://img.shields.io/badge/database-PostgreSQL-4169E1?logo=postgresql)
![Python](https://img.shields.io/badge/Python-monitoring-3776AB?logo=python)

## Overview

**Finmech Network Monitor (FNM)** is an in-house network monitoring project designed to provide centralized visibility into infrastructure health without depending on a conventional third-party monitoring stack.

The platform combines a Python/FastAPI monitoring backend, a Next.js dashboard, PostgreSQL persistence, device polling, alert lifecycle handling, and SNMP-oriented monitoring capabilities.

> **Portfolio notice:** This public repository is a sanitized project showcase. Production source code, credentials, internal addressing, SNMP secrets, and organization-specific configuration are intentionally excluded.

## Core Capabilities

- Device inventory and centralized monitoring
- UP / DOWN availability checks
- Latency monitoring
- Packet-loss monitoring
- Device health summary
- Active alert dashboard
- Alert history
- Alert acknowledgement workflow
- Automatic recovery handling
- Interface-level monitoring
- Duplicate incident prevention
- Extensible SNMP monitoring design
- REST API for dashboard and monitoring operations

## Architecture

```text
                    ┌─────────────────────────┐
                    │     Next.js Frontend    │
                    │    Monitoring Dashboard │
                    └────────────┬────────────┘
                                 │
                              REST API
                                 │
                    ┌────────────▼────────────┐
                    │       FastAPI API       │
                    │  Monitoring / Alerts    │
                    └───────┬─────────┬───────┘
                            │         │
                   ┌────────▼───┐ ┌──▼─────────────┐
                   │ PostgreSQL │ │ Polling Engine │
                   │  Database  │ │ ICMP / SNMP    │
                   └────────────┘ └───────┬────────┘
                                         │
                                  Network Devices
```

## Technology Stack

| Layer | Technology |
| --- | --- |
| Frontend | Next.js / React |
| Backend | FastAPI / Python |
| Database | PostgreSQL |
| Monitoring | Python polling engine |
| Network telemetry | ICMP / SNMP |
| API | REST |
| Platform | Linux / Ubuntu |

## Alert Lifecycle

FNM tracks incidents through a structured lifecycle:

```text
Device Healthy
     │
     ▼
Failure Detected
     │
     ▼
ACTIVE Alert
     │
     ├────► ACKNOWLEDGED
     │
     ▼
Service Restored
     │
     ▼
RECOVERED
```

The design prevents repeated polling failures from generating unnecessary duplicate open incidents for the same monitored condition.

## Interface Monitoring

The monitoring engine is designed to track network-interface operational state and detect transitions such as:

```text
UP → DOWN     Create critical interface incident
DOWN → DOWN   Keep existing incident / prevent duplicate
DOWN → UP     Recover existing incident
```

## API Design

Representative API areas include:

```text
/api/devices
/api/dashboard/summary
/api/alerts/active
/api/alerts/history
```

Exact production configuration and internal endpoints are not published in this repository.

## Security & Public Repository Policy

The following information is intentionally **not committed**:

- Production credentials
- Database passwords
- SNMP community strings
- API secrets
- Internal IP addressing
- Private infrastructure topology
- Organization-specific production configuration
- Sensitive logs or monitoring data

Example values should always be used when documenting deployments publicly.

## Roadmap

- [x] Device availability monitoring
- [x] Latency and packet-loss monitoring
- [x] Dashboard summary
- [x] Alert creation
- [x] Alert acknowledgement
- [x] Alert recovery
- [x] Alert history
- [x] Interface DOWN / recovery lifecycle
- [x] Duplicate incident prevention
- [ ] Extended SNMP metrics
- [ ] Interface bandwidth visualization
- [ ] CPU / memory / environmental metrics
- [ ] Device discovery
- [ ] Notification integrations
- [ ] Reporting and SLA dashboards
- [ ] Role-based access control

## Documentation

- **[Architecture](docs/ARCHITECTURE.md)** — system components and alert-state design
- **[Features](docs/FEATURES.md)** — monitoring, alerting, interface and dashboard capabilities
- **[API Examples](docs/API_EXAMPLES.md)** — sanitized representative REST API examples
- **[Roadmap](docs/ROADMAP.md)** — completed, in-progress and planned work
- **[Project Structure](docs/PROJECT_STRUCTURE.md)** — representative application organization
- **[Security Policy](SECURITY.md)** — rules for keeping sensitive infrastructure data private

## Screenshots

Screenshots of the sanitized dashboard can be added under a future `docs/screenshots/` directory.

> Before publishing screenshots, internal IP addresses, hostnames, usernames, customer information, and other sensitive infrastructure data should be masked.

## Project Goals

FNM is being developed as a practical infrastructure-monitoring platform with an emphasis on:

1. **Visibility** — clear infrastructure health at a glance.
2. **Reliability** — predictable polling and incident handling.
3. **Operational usefulness** — actionable alerts instead of unnecessary noise.
4. **Extensibility** — support for additional protocols, metrics, and device types.
5. **Security** — separation of public documentation from sensitive production information.

## Author

**Adarsh Kumar Singh**

IT Infrastructure • Network Monitoring • Systems Administration • Cybersecurity • Automation

GitHub: [@akbengaltiger](https://github.com/akbengaltiger)

---

### Disclaimer

This repository documents the architecture and development journey of the project for portfolio and technical demonstration purposes. It does not expose confidential production infrastructure or proprietary organizational data.
