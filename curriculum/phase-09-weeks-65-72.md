# Phase 9 — Weeks 65–72: Performance, Databases, Kafka, Event-Driven Systems

## Week 65 — Load testing and capacity planning
Day 1: throughput, concurrency, latency, saturation. Day 2: run controlled load test against API. Day 3: graph p50/p95/p99 and error rate. Day 4: push until bottleneck appears and identify first saturated resource. Day 5: estimate capacity headroom and scaling threshold. Day 6: interview drill on capacity planning assumptions. Day 7: write load-test report with safe limits.

## Week 66 — Linux performance troubleshooting
Day 1: CPU load/run queue concepts and `top`/`ps`. Day 2: memory, swap, page pressure using `free`, `/proc`, available tools. Day 3: disk I/O concepts and `df`, `du`, iostat if available. Day 4: controlled CPU/memory/disk pressure lab. Day 5: distinguish host saturation from app bug. Day 6: timed Linux performance interview. Day 7: performance triage runbook.

## Week 67 — Network performance troubleshooting
Day 1: latency, packet loss, bandwidth, retransmission concepts. Day 2: DNS timing and connection timing with curl. Day 3: use ping/traceroute-style tools appropriately and understand limits. Day 4: slow/downstream timeout simulation. Day 5: connection pool and socket exhaustion concepts. Day 6: interview drill from symptom to network layer. Day 7: network performance checklist.

## Week 68 — Database performance and failure modes
Day 1: indexes/query plans. Day 2: connection pooling. Day 3: lock/contention concepts and transactions. Day 4: slow query lab; gather evidence before indexing. Day 5: DB saturation/backpressure and timeouts. Day 6: interview drill: “DB CPU is 90%, app latency rising.” Day 7: database runbook.

## Week 69 — Distributed database concepts
Day 1: replication and failover. Day 2: quorum/consistency levels conceptually. Day 3: partitioning/sharding. Day 4: replica lag/stale-read tabletop. Day 5: backup vs replication revisited. Day 6: choose relational vs distributed store for scenarios. Day 7: architecture decision record.

## Week 70 — Queues and stream processing
Day 1: queue vs stream. Day 2: partitions/order/consumer groups concepts. Day 3: delivery semantics: at-most/at-least/exactly-once claims. Day 4: poison message and dead-letter handling. Day 5: backpressure/lag monitoring. Day 6: interview drill on async architecture. Day 7: worker design review.

## Week 71 — Kafka fundamentals
Day 1: broker/topic/partition/offset. Day 2: run local Kafka-compatible lab or study with executable tooling available. Day 3: produce/consume events and inspect offsets. Day 4: consumer failure/rebalance drill. Day 5: retention and key-based partitioning. Day 6: interview drill on ordering/scaling. Day 7: add event flow diagram.

## Week 72 — Event-driven architecture
Day 1: events vs commands. Day 2: design event for user-created/job-requested flow. Day 3: schema evolution/versioning concepts. Day 4: duplicate/out-of-order event failure lab. Day 5: idempotent consumer design. Day 6: interview system-design drill using queue/stream. Day 7: phase checkpoint: synchronous API + DB/cache + async worker architecture and failure analysis.
