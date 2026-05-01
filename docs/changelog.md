# Changelog - AIP System Control Plane API Specification

## 1.0.0 - Initial baseline

- Introduced canonical System API contract for control-plane lifecycle operations.
- Added resources:
  - `POST /analysis-jobs`
  - `GET /analysis-jobs/{jobid}`
  - `GET /metrics`
  - `GET /health-check/alive` and `GET /health-check/ready`
- Added examples for submit, retrieve, and metrics responses.
- Added operation names aligned with MCP mapping catalogue.
