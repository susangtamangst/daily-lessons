# Phase 4 — Weeks 25–32: Grafana, Logs, Traces, SRE, Incidents, CI, Security

## Week 25 — Grafana dashboards
Day 1: connect Grafana to Prometheus and explore metrics. Day 2: build RED dashboard (rate/errors/duration). Day 3: add Kubernetes/pod views. Day 4: create a misleading dashboard intentionally and fix bad aggregation/units. Day 5: add annotations for deployments. Day 6: interview drill on useful vs vanity metrics. Day 7: publish dashboard screenshots and explain each panel.

## Week 26 — Logging pipelines
Day 1: define structured JSON logging fields: timestamp, level, request_id, route, status, duration. Day 2: centralize logs with a lightweight Loki-style stack or equivalent. Day 3: query by service, pod, request_id. Day 4: failure lab where only logs reveal malformed input. Day 5: add correlation IDs across calls. Day 6: discuss log retention, PII, cardinality, cost. Day 7: write logging standards for the project.

## Week 27 — OpenTelemetry and tracing
Day 1: learn span, trace, context propagation. Day 2: instrument health API and one dependency call. Day 3: visualize trace waterfall. Day 4: inject slow DB/downstream and identify latency span. Day 5: correlate trace_id with logs. Day 6: explain traces vs metrics vs logs in an interview. Day 7: capture one complete incident using all three signals.

## Week 28 — SLIs, SLOs, error budgets
Day 1: define availability and latency SLIs. Day 2: write a realistic 99.9% availability SLO and calculate allowed bad time conceptually. Day 3: build SLI queries from Prometheus data. Day 4: simulate errors and watch budget burn. Day 5: define fast/slow burn alert ideas. Day 6: interview drill on SLA vs SLO vs SLI. Day 7: add `sre/slo.md` with rationale and exclusions.

## Week 29 — Alerting and on-call
Day 1: learn symptom-based vs cause-based alerts. Day 2: create high-error-rate alert. Day 3: create high-latency alert. Day 4: intentionally make a noisy alert and tune it. Day 5: add runbook link/owner/severity fields. Day 6: mock on-call page and verbal triage. Day 7: review alerts against “actionable, urgent, user-impacting.”

## Week 30 — Incident response and postmortems
Day 1: incident roles, timeline, mitigation vs diagnosis. Day 2: run 30-minute service outage drill. Day 3: gather evidence without changing multiple variables at once. Day 4: write timeline and root cause. Day 5: create prevention actions with owners/verification. Day 6: behavioral interview story using STAR plus technical depth. Day 7: publish blameless postmortem in `incidents/`.

## Week 31 — GitHub Actions CI
Day 1: workflow/job/step/event/secrets/artifacts concepts. Day 2: CI for lint + unit tests. Day 3: build container image on PR/main. Day 4: break a test/build and diagnose from logs. Day 5: add caching and artifact/image tagging with commit SHA. Day 6: interview drill on CI vs CD and safe promotion. Day 7: clean clone → PR → passing CI → merge.

## Week 32 — Container security and supply chain
Day 1: minimize base image and run as non-root. Day 2: scan dependencies/image with an available scanner. Day 3: understand SBOM and image provenance concepts. Day 4: inject vulnerable/outdated dependency and inspect result. Day 5: pin versions/digests where appropriate and document update strategy. Day 6: discuss secrets in images and least privilege. Day 7: phase checkpoint: secure, tested, observable image built by CI with documented controls.
