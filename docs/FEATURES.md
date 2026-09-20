# FNM Features

## Device Monitoring

FNM is designed to maintain a centralized inventory of monitored network devices and continuously evaluate their operational state.

Current project capabilities include:

- Device registration and monitoring
- UP / DOWN state tracking
- Health summary
- Latency measurement
- Packet-loss measurement
- Manual/on-demand polling support
- Monitoring enable/disable state

## Alert Management

FNM uses an incident-oriented alert lifecycle rather than treating every failed poll as a separate event.

### Supported lifecycle

```text
Healthy
  |
Failure detected
  v
ACTIVE
  |
  +---- Acknowledge ----> ACKNOWLEDGED
  |
Recovery detected
  v
RECOVERED
```

Capabilities include:

- Critical device-down alerts
- Active-alert view
- Alert acknowledgement
- Recovery handling
- Alert history
- Device information snapshots for historical records
- Duplicate open-incident prevention

## Interface Monitoring

Interface monitoring tracks operational-state transitions.

| Transition | Action |
| --- | --- |
| UP → DOWN | Create interface-down incident |
| DOWN → DOWN | Keep existing incident; do not duplicate |
| DOWN → UP | Recover the open incident |

## Dashboard

The dashboard layer is intended to provide a concise operational view of:

- Total monitored devices
- Online/offline state
- Infrastructure health percentage
- Device list and current state
- Active incidents
- Historical alerts

## SNMP Direction

FNM is designed to expand beyond reachability checks through SNMP-based telemetry, including future support for:

- Interface inventory
- Interface utilization
- CPU and memory
- Device uptime
- Environmental metrics where supported
- Vendor/device-specific telemetry

## Design Principles

**Operational clarity** — show actionable information rather than unnecessary noise.

**Incident integrity** — maintain a clear lifecycle for each monitored failure.

**Extensibility** — allow new device types, protocols, and metrics to be introduced over time.

**Security** — keep credentials and internal infrastructure information outside public source and documentation.
