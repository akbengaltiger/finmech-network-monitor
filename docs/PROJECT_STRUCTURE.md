# Project Structure

The public repository currently focuses on sanitized technical documentation. The production implementation is intentionally not mirrored here.

A representative FNM application structure is:

```text
fnm/
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   ├── monitoring/
│   │   ├── alerts/
│   │   └── main.py
│   ├── tests/
│   └── requirements.txt
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── lib/
│   └── package.json
│
├── docs/
│   ├── ARCHITECTURE.md
│   ├── FEATURES.md
│   ├── API_EXAMPLES.md
│   ├── ROADMAP.md
│   └── PROJECT_STRUCTURE.md
│
├── .env.example
├── .gitignore
├── SECURITY.md
└── README.md
```

## Backend Responsibilities

The backend is conceptually separated into:

- API routes
- Database models and schemas
- Device services
- Polling/monitoring engine
- Alert state management
- SNMP integrations
- Background operational logic

## Frontend Responsibilities

The frontend is responsible for:

- Dashboard presentation
- Device inventory views
- Device health/state
- Active alerts
- Alert history
- Administrative workflows

## Documentation Boundary

This structure is representative rather than a disclosure of private production layout. Public documentation should remain useful technically without exposing organization-specific implementation details, secrets, internal addressing, or private topology.
