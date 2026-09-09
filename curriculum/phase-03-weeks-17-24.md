# Phase 3 — Weeks 17–24: Ingress, Troubleshooting, Helm, Data, Reliability, Metrics

## Week 17 — Ingress and traffic routing
**Day 1.** Learn north-south traffic, Ingress vs Service. Install a lightweight ingress controller in kind and inspect its resources.
**Day 2.** Route `/` to health API through Ingress; verify host/path matching.
**Day 3.** Trace request path: client → ingress controller → Service → endpoint → Pod.
**Day 4.** Failure lab: wrong host/path or backend Service name. Diagnose from ingress events/logs plus Service endpoints.
**Day 5.** Add TLS conceptually using self-signed/local certificate if practical; explain termination location.
**Day 6.** Interview drill: Ingress vs LoadBalancer Service vs API gateway.
**Day 7.** Create architecture diagram of complete request flow.

## Week 18 — Kubernetes troubleshooting I
**Day 1.** Build a symptom-first checklist: Pending, CrashLoopBackOff, ImagePullBackOff, Running-but-unhealthy.
**Day 2.** CrashLoop lab: bad startup command. Use `get`, `describe`, `logs`, `logs --previous`.
**Day 3.** Pending lab: impossible resource request. Read scheduler Events before changing YAML.
**Day 4.** Service outage lab: selector mismatch. Trace Service → endpoints → Pod labels.
**Day 5.** DNS lab: debug Service-name resolution from a disposable Pod.
**Day 6.** Timed incident: diagnose one injected fault in 15 minutes while narrating evidence.
**Day 7.** Write incident 001 with symptoms, impact, evidence, root cause, fix, prevention.

## Week 19 — Kubernetes troubleshooting II
**Day 1.** Learn node conditions and pressure signals. Inspect `kubectl describe node`.
**Day 2.** Probe-failure lab: app responds slowly or wrong status; inspect readiness/liveness events.
**Day 3.** Port-mismatch lab: container listens 8000, Service targets 8080. Diagnose without guessing.
**Day 4.** Config failure lab: missing env var/Secret key causing startup failure.
**Day 5.** Resource failure lab: controlled OOMKilled; distinguish app exception from kernel/runtime termination.
**Day 6.** Interview drill: “A Deployment is healthy but users get 503s.” Walk layer by layer.
**Day 7.** Create reusable Kubernetes triage runbook and a command cheat sheet.

## Week 20 — Helm and packaging
**Day 1.** Learn chart, template, values, release. Install Helm and inspect a simple generated chart.
**Day 2.** Convert health API manifests into a Helm chart.
**Day 3.** Parameterize image tag, replicas, resources, Service port, environment name.
**Day 4.** Failure lab: invalid value/template output. Use `helm template`, `helm lint`, `--dry-run`.
**Day 5.** Create dev/prod-like values files with different replica/resource settings.
**Day 6.** Interview drill: Helm benefits, dangers of over-templating, Helm vs Kustomize concepts.
**Day 7.** Clean install → upgrade → rollback → uninstall; document release lifecycle.

## Week 21 — PostgreSQL fundamentals
**Day 1.** Learn relational basics: table, row, primary key, index, transaction. Run PostgreSQL locally/containerized.
**Day 2.** Add a simple `users` table and CRUD endpoints to API.
**Day 3.** Learn connection strings, connection pooling concept, migration concept.
**Day 4.** Failure lab: wrong credentials / DB unavailable. Ensure readiness reflects dependency health appropriately.
**Day 5.** Learn basic index behavior using `EXPLAIN` conceptually and simple query comparison.
**Day 6.** Interview drill: why not store everything in memory? durability, consistency, concurrency.
**Day 7.** Document schema and database failure modes.

## Week 22 — Redis and caching
**Day 1.** Learn key/value store, TTL, cache hit/miss, eviction at a high level. Run Redis locally.
**Day 2.** Cache one read endpoint; measure first vs repeated request behavior.
**Day 3.** Add TTL and explain stale data tradeoff.
**Day 4.** Failure lab: Redis unavailable. Design app to degrade gracefully where appropriate.
**Day 5.** Learn cache-aside pattern and invalidation difficulty.
**Day 6.** Interview drill: when Redis helps and when it creates consistency risk.
**Day 7.** Draw request flow with PostgreSQL + Redis and document fallback behavior.

## Week 23 — Application reliability patterns
**Day 1.** Timeouts: add explicit downstream timeout and explain why infinite waits are dangerous.
**Day 2.** Retries: add bounded retry with backoff for a safe/idempotent operation.
**Day 3.** Idempotency: create a request example where duplicate execution matters.
**Day 4.** Failure lab: slow dependency. Compare behavior without timeout vs with timeout/retry.
**Day 5.** Learn circuit breaker and bulkhead concepts; document where they would fit.
**Day 6.** Interview drill: “Retries are making an outage worse—why?” discuss retry storms/backoff/jitter.
**Day 7.** Add reliability design note to repo with chosen timeout/retry policy.

## Week 24 — Metrics with Prometheus
**Day 1.** Learn counter, gauge, histogram, label. Instrument request count and latency.
**Day 2.** Run Prometheus and scrape health API metrics.
**Day 3.** Query request rate, error rate, latency distributions using basic PromQL.
**Day 4.** Failure lab: generate 500s and observe metric change before reading logs.
**Day 5.** Add dependency-health and process/runtime metrics selectively; avoid unbounded labels.
**Day 6.** Interview drill: metrics vs logs vs traces; cardinality risk.
**Day 7.** Phase checkpoint: demonstrate user request → app → Redis/Postgres plus Prometheus evidence during one injected failure.
