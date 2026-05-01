# Changelog - AIP System Control Plane API Specification

## 1.0.1 - Governance (Anypoint Best Practices)

- Renamed RAML JSON property names from snake_case to **camelCase** (for example `jobId`, `correlationId`, `sourceType`, `requestsTotal`).
- Declared mandatory `Content-Type` header metadata on `200` and `202` success responses to satisfy the ruleset.

## 1.0.0 - Initial baseline

- Introduced canonical System API contract for control-plane lifecycle operations.
- Added resources:
  - `POST /analysis-jobs`
  - `GET /analysis-jobs/{jobid}`
  - `GET /metrics`
  - `GET /health-check/alive` and `GET /health-check/ready`
- Added examples for submit, retrieve, and metrics responses.
- Added operation names aligned with MCP mapping catalogue.
