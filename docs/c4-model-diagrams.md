# C4 Model Diagrams - AIP System Control Plane API Specification

## Purpose

Provide a contract-centred architecture view for this System API specification, focusing on job lifecycle behaviour and control-plane interoperability.

## C4 Level 1 - Contract Context

```mermaid
flowchart LR
    prcApi["aip-mule-prc-log-intelligence-api-app"]
    sysApp["aip-mule-sys-control-plane-api-app"]
    spec["aip-mule-sys-control-plane-api-spec<br/>(Contract Source of Truth)"]

    prcApi -->|"Consumes control-plane contract"| spec
    spec -->|"Implemented by runtime"| sysApp
```

## C4 Level 2 - Contract Containers

```mermaid
flowchart TD
    subgraph spec["aip-mule-sys-control-plane-api-spec"]
        raml["Root RAML Contract<br/>aip-mule-sys-control-plane-api.raml"]
        docs["Contract Docs<br/>documentation.raml + docs/contract-overview.md"]
        examples["Examples<br/>examples/*.raml"]
        exchange["Exchange Descriptor<br/>exchange.json"]
        fragments["Shared Fragments<br/>mule-utility-common-fragment"]
        governance["Governance Rules<br/>anypoint-best-practices"]
    end

    docs --> raml
    examples --> raml
    exchange --> raml
    raml --> fragments
    raml --> governance
```

## C4 Level 3 - Contract Components

```mermaid
flowchart LR
    auth["Security Scheme<br/>core-lib.token"]
    submit["POST /analysis-jobs"]
    status["GET /analysis-jobs/{jobid}"]
    metrics["GET /metrics"]
    health["GET /health-check/alive + /ready"]
    model["Types<br/>SubmitJobRequest, SubmitJobResponse, Job, Metrics"]

    auth --> submit
    auth --> status
    auth --> metrics
    model --> submit
    model --> status
    model --> metrics
    model --> health
```

## Update Triggers

Update these diagrams whenever lifecycle semantics, payload models, security controls, or MCP binding-related operation naming changes.
