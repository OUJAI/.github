# Contributing to OUJAI — Hospital Digital Twin

Welcome to the **OUJAI** graduation project! Because we are a four-person team working across eight focused repositories over an 18-week timeline, we follow a lightweight, disciplined Git workflow.

## 1. The Lightweight 8-Step Workflow

Every change across every OUJAI repository follows this exact cycle:

```text
Issue → Feature Branch → Commit → Pull Request → Peer Review → CI Checks → Merge → Integration Test
```

1. **Issue:** Open an issue using the repository templates (`Feature Task`, `Bug Report`, or `Documentation Task`) before writing code. Assign it to yourself and link it to the current week's milestone.
2. **Feature Branch:** Branch off `main` using the standard naming convention:
   - `feat/<issue-id>-<short-slug>` (e.g., `feat/12-bed-state-machine`)
   - `fix/<issue-id>-<short-slug>` (e.g., `fix/19-mqtt-reconnect`)
   - `docs/<issue-id>-<short-slug>` (e.g., `docs/04-openapi-contracts`)
   - `ds/<issue-id>-<short-slug>` (e.g., `ds/22-seasonal-naive-baseline`)
3. **Commit:** Write atomic commits using Conventional Commits (`feat:`, `fix:`, `docs:`, `test:`, `refactor:`, `chore:`).
4. **Pull Request:** Open a PR against `main` and complete all checkboxes in `PULL_REQUEST_TEMPLATE.md`.
5. **Peer Review:** At least **1 approving review** is required (from the repository's Primary Owner or, if opened by the Primary Owner, from the designated Supporting Contributor).
6. **CI Checks:** All automated GitHub Actions checks (linting, unit tests, schema checks) must pass.
7. **Merge:** Use **Squash and Merge** to keep `main` history clean and linear.
8. **Integration Test:** If the change touches APIs, MQTT payloads, or WebSocket events, verify end-to-end compatibility using `oujai-infrastructure` Docker Compose.

## 2. Contract-First Rule
Never change a REST endpoint, WebSocket payload, MQTT topic (`oujai/v1/...`), or KPI formula in code without first updating (or co-submitting a PR to) [`oujai-docs`](https://github.com/oujai/oujai-docs).

## 3. Synthetic Data & Zero-Secret Mandate
- **100% Synthetic Data:** Never commit real patient names, national IDs, medical record numbers, or clinical notes.
- **Zero Secrets:** Never commit `.env` files, JWT signing keys, database passwords, or GitHub tokens. Always use `.env.example` with safe placeholder values.
