# Contract Overview - AIP System Control Plane API

## Context and Intent

This System API provides canonical control-plane operations for analysis job submission, lifecycle retrieval, and lightweight metrics.

Design intent:

- Keep Process API integration stable while internal implementation evolves.
- Preserve compatibility with retired Go API semantics where useful for migration.
- Align with contract-first, security-by-design, and observability-by-contract principles.

## Unified Contract Draft (RAML)

Reference: `aip-mule-sys-control-plane-api.raml`

Template and fragment alignment:

- Reuses `mule-utility-common-fragment` via `uses` (`core-lib` alias).
- Uses shared client-id enforcement scheme through `core-lib.token`.
- Reuses shared health-check resource types: `core-lib.healthCheckAlive`, `core-lib.healthCheckReady`.

Key operations:

- `POST /analysis-jobs`: submit a new analysis job and return accepted lifecycle state.
- `GET /analysis-jobs/{jobid}`: return deterministic lifecycle details.
- `GET /metrics`: expose counters for baseline observability.

## Compatibility Notes

- Operation names are aligned to MCP catalogue mapping:
  - `postSysControlPlaneAnalysisJob`
  - `getSysControlPlaneAnalysisJobById`
  - `getSysControlPlaneMetrics`
- JSON property names follow **camelCase** (Design Center Anypoint Best Practices). Canonical anchors include `jobId`, `status`, and `correlationId`.

## Security and Compliance Controls

- Client ID policy enforcement through shared token scheme.
- Canonical error model via shared fragment trait.
- No raw secrets or credentials in request/response payloads.

## Review and Evolution

Update this document when:

- RAML resources or schema fields change.
- Job lifecycle semantics change.
- MCP bindings for these operations are revised.

Breaking contract changes require explicit versioning impact assessment.
