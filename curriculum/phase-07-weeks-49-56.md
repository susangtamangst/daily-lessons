# Phase 7 — Weeks 49–56: Async Systems, System Design, Year-1 Capstone, Advanced Kubernetes

## Week 49 — Queues, async processing, backpressure
Day 1: learn queue, producer, consumer, acknowledgement, retry, dead-letter queue. Day 2: add a simple background worker to the project using a lightweight queue. Day 3: measure queue depth and processing latency. Day 4: failure lab: slow consumer causes backlog; diagnose from queue depth/worker logs. Day 5: implement bounded retry/idempotent handling. Day 6: interview drill on queue vs synchronous API. Day 7: document backpressure strategy.

## Week 50 — Caching, consistency, idempotency
Day 1: cache-aside/write-through concepts. Day 2: build cache-aside read path. Day 3: create stale-cache scenario and define acceptable TTL. Day 4: duplicate-request lab; add idempotency key concept to write path. Day 5: discuss eventual consistency and invalidation. Day 6: interview drill: “How do you prevent duplicate payment/job processing?” Day 7: write consistency tradeoff note.

## Week 51 — System design foundations
Day 1: requirements, scale assumptions, APIs, data model. Day 2: capacity estimation basics. Day 3: load balancing, stateless services, caches, databases. Day 4: identify single points of failure in your own platform. Day 5: draw high-level design and deep-dive one component. Day 6: 30-minute mock design explanation. Day 7: critique and revise based on bottlenecks/failure modes.

## Week 52 — Year 1 capstone
Day 1: inventory everything built; remove dead/demo-only pieces. Day 2: clean deployment from README on local Kubernetes. Day 3: run observability stack and verify SLO/dashboard. Day 4: inject one unknown failure and perform timed diagnosis. Day 5: deploy or validate AWS/EKS version if budget permits; otherwise Terraform plan + architecture walkthrough. Day 6: give 20-minute portfolio presentation aloud. Day 7: write Year-1 retrospective: strengths, weak spots, incidents, next-year objectives.

## Week 53 — Advanced Kubernetes scheduling
Day 1: node selectors/labels. Day 2: node affinity/anti-affinity. Day 3: taints/tolerations. Day 4: failure lab: Pod Pending from unsatisfied scheduling rule. Day 5: topology spread constraints and availability. Day 6: interview drill on scheduler decisions. Day 7: design resilient placement for API replicas.

## Week 54 — Autoscaling
Day 1: HPA metrics and target utilization. Day 2: generate load and observe scale-out/in. Day 3: VPA concepts and why it interacts with HPA. Day 4: cluster autoscaling concepts; compare managed approaches. Day 5: failure lab: poor requests cause bad scaling behavior. Day 6: interview drill on horizontal vs vertical scaling. Day 7: write scaling policy tied to SLO/capacity data.

## Week 55 — NetworkPolicy and zero-trust basics
Day 1: default-open Kubernetes networking mental model. Day 2: create namespace/pod isolation policy. Day 3: permit only API→DB traffic. Day 4: failure lab: deny legitimate traffic, diagnose with policy/labels/DNS/TCP checks. Day 5: define ingress/egress policy strategy. Day 6: interview drill on segmentation vs authentication. Day 7: document allowed communication graph.

## Week 56 — Service mesh concepts
Day 1: sidecar/data-plane/control-plane mental model. Day 2: understand mTLS, traffic policy, telemetry use cases. Day 3: evaluate whether your project actually needs a mesh. Day 4: failure tabletop: mesh policy blocks service traffic. Day 5: compare mesh vs app/library/platform features. Day 6: interview drill on costs/complexity. Day 7: write an ADR accepting or rejecting service mesh for the lab.
