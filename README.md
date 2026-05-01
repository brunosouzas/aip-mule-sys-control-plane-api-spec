# AIP Mule System Control Plane API - Specification

This repository is the contract source of truth for the `aip-mule-sys-control-plane-api` System API.

## Purpose

Provide a stable, canonical contract for analysis job lifecycle operations (submit, status retrieval, lightweight metrics) used by the Process API orchestration layer.

## Scope

- Define RAML resources, types, examples, and error semantics.
- Preserve compatibility with the legacy Go control-plane surface where practical.
- Enforce canonical payloads for MCP and agent tool bindings.

## Source of Truth

- Main contract file: `aip-mule-sys-control-plane-api.raml`
- Exchange descriptor: `exchange.json`

## Shared Governance Assets

This specification reuses the common fragment baseline:

- Template baseline: `mule-utility-template-spec` `1.0.0`
- Common fragment: `mule-utility-common-fragment` `1.0.0`

## Repository Documents

- `docs/contract-overview.md`: intent, operation semantics, and compatibility controls.
- `docs/changelog.md`: contract evolution log and compatibility notes.
- `docs/c4-model-diagrams.md`: C4 context/container/component diagrams for this specification repository.

## Ownership and Update Triggers

Update this repository when any of the following occurs:

- Contract path/query/response shape changes.
- New canonical fields or statuses are introduced.
- Messaging semantics change (`analysis.debug.requested.v1` compatibility).
- Security controls or data classification handling rules change.

All contract updates require review for compatibility impact and alignment with API contract principles.
