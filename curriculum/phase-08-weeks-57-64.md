# Phase 8 — Weeks 57–64: Kubernetes Security, Policy, Secrets, Advanced Observability

## Week 57 — Kubernetes security hardening
Day 1: attack surface: API, nodes, images, identities, network. Day 2: run workloads as non-root/read-only where practical. Day 3: SecurityContext and Linux capabilities. Day 4: failure lab from overly restrictive permissions; diagnose without simply disabling controls. Day 5: image provenance/scanning review. Day 6: interview drill on pod hardening. Day 7: hardening checklist.

## Week 58 — RBAC and multi-tenancy
Day 1: Role/ClusterRole/RoleBinding/ServiceAccount. Day 2: create read-only namespace role. Day 3: verify permissions with `kubectl auth can-i`. Day 4: failure lab: forbidden API request; trace identity → binding → role rules. Day 5: namespace-based tenancy design. Day 6: interview drill on least privilege. Day 7: RBAC matrix for platform users/services.

## Week 59 — Policy as code
Day 1: admission control mental model. Day 2: define policies for required labels/resources/non-root. Day 3: test good/bad manifests with a policy engine concept/tool available to you. Day 4: failure lab: blocked deployment; read policy result and fix spec. Day 5: exception/break-glass process. Day 6: discuss preventive vs detective controls. Day 7: publish policy standards.

## Week 60 — Secrets management
Day 1: why base64 Kubernetes Secrets are not encryption by themselves. Day 2: external secret-store concepts. Day 3: rotate a mock credential with minimal downtime. Day 4: failure lab: stale secret/permission issue. Day 5: secret injection vs mounted file tradeoffs. Day 6: interview drill on secret lifecycle. Day 7: write rotation/runbook and never commit real credentials.

## Week 61 — Advanced observability
Day 1: telemetry architecture and ownership. Day 2: golden signals per service. Day 3: correlation across metrics/logs/traces. Day 4: incident where one signal is misleading and another reveals cause. Day 5: dashboard hierarchy from fleet → service → instance. Day 6: interview drill on observability vs monitoring. Day 7: refactor noisy telemetry.

## Week 62 — Prometheus internals and cardinality
Day 1: scrape model/time series/labels. Day 2: inspect target health and scrape errors. Day 3: identify high-cardinality label design. Day 4: failure lab: cardinality explosion tabletop and remediation. Day 5: recording rules concept. Day 6: explain histogram buckets and percentile caveats. Day 7: metrics naming/cardinality standards.

## Week 63 — Tracing-driven debugging
Day 1: sampling and propagation. Day 2: trace cross-service request. Day 3: identify slow span and downstream dependency. Day 4: break propagation and diagnose missing trace continuity. Day 5: add useful span attributes without sensitive data. Day 6: interview drill on when tracing pays off. Day 7: incident report centered on trace evidence.

## Week 64 — Performance profiling
Day 1: CPU vs memory vs I/O bottlenecks. Day 2: profile Python endpoint under load. Day 3: compare latency before/after one optimization. Day 4: failure lab: CPU-heavy path and Kubernetes throttling evidence. Day 5: memory profiling/leak concepts. Day 6: interview drill: “service slow but CPU low—what next?” Day 7: phase checkpoint with measured performance report.
