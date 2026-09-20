# API Examples

These examples demonstrate the intended API shape using **fictional documentation values only**. They are not production endpoints or production data.

## Device List

```http
GET /api/devices
```

Example response:

```json
[
  {
    "id": 1,
    "name": "Example Gateway",
    "ip_address": "192.0.2.10",
    "type": "gateway",
    "location": "Example Site",
    "enabled": true,
    "status": "UP"
  }
]
```

## Dashboard Summary

```http
GET /api/dashboard/summary
```

Example response:

```json
{
  "total_devices": 10,
  "online": 9,
  "offline": 1,
  "health_percentage": 90
}
```

## Poll a Device

```http
POST /api/devices/1/poll
```

Example response:

```json
{
  "device_id": 1,
  "status": "UP",
  "latency_ms": 1.25,
  "packet_loss": 0
}
```

## Active Alerts

```http
GET /api/alerts/active
```

Example response:

```json
[
  {
    "id": 42,
    "device_id": 7,
    "alert_type": "DEVICE_DOWN",
    "severity": "CRITICAL",
    "status": "ACTIVE",
    "title": "Example Switch is DOWN"
  }
]
```

## Alert History

```http
GET /api/alerts/history
```

Historical records can retain sanitized device snapshots so an incident remains understandable even if inventory data changes later.

## Security Note

Documentation examples use addresses from ranges intended for examples. Never publish real internal addresses, authentication tokens, database credentials, SNMP communities, or production payloads in this repository.
