# FNM Development Roadmap

This roadmap describes the intended technical direction of Finmech Network Monitor.

## Foundation — Completed

- [x] FastAPI backend foundation
- [x] Next.js frontend foundation
- [x] PostgreSQL persistence
- [x] Device inventory API
- [x] Device polling
- [x] Availability state
- [x] Latency monitoring
- [x] Packet-loss monitoring
- [x] Dashboard summary

## Alerting — Completed

- [x] Device-down incident creation
- [x] Active alerts
- [x] Alert acknowledgement
- [x] Recovery workflow
- [x] Alert history
- [x] Historical device snapshots
- [x] Duplicate incident prevention

## Interface Monitoring — In Progress

- [x] Interface state model
- [x] UP → DOWN detection
- [x] DOWN → UP recovery
- [x] Duplicate interface-incident prevention
- [ ] Broader interface discovery
- [ ] Interface utilization metrics
- [ ] Error/discard counters

## SNMP & Metrics — Planned

- [ ] Expanded SNMP polling
- [ ] CPU utilization
- [ ] Memory utilization
- [ ] Device uptime
- [ ] Interface bandwidth
- [ ] Environmental sensors where supported
- [ ] Vendor-specific metrics

## Platform — Planned

- [ ] Authentication
- [ ] Role-based access control
- [ ] Notification integrations
- [ ] Device discovery workflow
- [ ] Maintenance windows
- [ ] Reporting
- [ ] SLA/availability reporting
- [ ] Audit trail
- [ ] Backup/restore documentation

## UI & Operations — Planned

- [ ] Improved device detail pages
- [ ] Historical charts
- [ ] Alert filtering
- [ ] Search and grouping
- [ ] Location/site views
- [ ] Responsive dashboard refinements

## Public Showcase

- [x] Sanitized README
- [x] Architecture documentation
- [x] Security policy
- [x] Safe environment template
- [x] Feature documentation
- [x] Sanitized API examples
- [x] Development roadmap
- [ ] Sanitized dashboard screenshots
- [ ] Demo environment, if appropriate

The roadmap may evolve as monitoring requirements and supported device types expand.
