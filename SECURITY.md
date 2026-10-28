# Security & Synthetic Data Policy — OUJAI

## 1. Synthetic-Data-Only Mandate
OUJAI is an academic Hospital Digital Twin graduation project (2026–2027).
- **Strictly Prohibited:** Real patient records, real hospital admission logs, patient names, clinical notes, diagnoses, or staff personal credentials.
- **Required:** All patient episodes, telemetry signals, and historical occupancy tables must be generated synthetically by `oujai-data-science` and `oujai-iot-simulator` using deterministic random seeds (`SEED=2026`).

## 2. Credential and Secret Management
- Do not hardcode PostgreSQL credentials, JWT secrets (`JWT_SECRET_KEY`), or MQTT broker passwords in source files, notebooks, or Dockerfiles.
- All repositories must ignore `.env`, `*.pem`, `*.key`, and local SQLite/dump files via `.gitignore`.
- If a credential or token is accidentally committed:
  1. Immediately revoke/rotate the credential.
  2. Notify Member 1 (IT Student / Organization Admin).
  3. Purge the secret from Git history before continuing development.

## 3. Reporting a Vulnerability or Data Policy Violation
Within the project team, open a confidential discussion or contact the Primary Owner of `.github` and `oujai-infrastructure` (Member 1 — IT Student).
