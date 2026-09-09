# Phase 13 — Weeks 97–104: Platform Design, Behavioral, Troubleshooting, AI Infrastructure, Final Capstone

## Week 97 — System design: deployment platform
Day 1: requirements: source, build, artifact, deploy, rollback, audit. Day 2: control-plane vs data-plane design. Day 3: build/registry/GitOps pipeline. Day 4: failure modes: bad release, unavailable cluster, partial rollout. Day 5: multi-tenant security and quotas. Day 6: 45-minute mock design. Day 7: final architecture document with tradeoffs.

## Week 98 — System design: log pipeline
Day 1: ingestion volume and retention assumptions. Day 2: agents/collectors/buffering. Day 3: indexing/storage/query tradeoffs. Day 4: backpressure and dropped-log failure modes. Day 5: tenancy, PII, cost controls. Day 6: mock design interview. Day 7: compare design to your own logging stack.

## Week 99 — Behavioral interview stories
Day 1: inventory 8 real stories from work/lab. Day 2: ownership story. Day 3: conflict/disagreement story. Day 4: failure/lesson story. Day 5: ambiguity/prioritization story. Day 6: practice concise STAR answers with technical depth. Day 7: record/refine stories so each has situation, action, measurable result, learning.

## Week 100 — Troubleshooting interview drills
Day 1: Linux service down. Day 2: Kubernetes users receive 503. Day 3: Pod Pending/OOMKilled. Day 4: AWS/EKS node cannot join. Day 5: database latency spike. Day 6: full 45-minute mixed incident while narrating hypotheses/evidence. Day 7: identify recurring weak layers and update runbooks.

## Week 101 — AI infrastructure fundamentals
Day 1: training vs inference, model artifact, tokenizer, context, batch, latency/throughput. Day 2: API-hosted vs local model serving tradeoffs. Day 3: CPU vs GPU inference and why VRAM matters. Day 4: containerize a tiny inference/mock AI service or integrate a safe API-backed model adapter. Day 5: expose health/readiness/metrics for AI workload. Day 6: interview drill on operational differences between normal API and model server. Day 7: architecture note for AI workload on your platform.

## Week 102 — LLM serving and GPU scheduling concepts
Day 1: model loading, quantization, batching, KV-cache concepts. Day 2: Kubernetes extended resources/device-plugin mental model. Day 3: node labels/taints for GPU workloads. Day 4: failure tabletop: GPU unavailable / OOM / slow inference. Day 5: autoscaling and queueing for inference. Day 6: compare local GPU, managed endpoint, and external API. Day 7: design GPU-ready cluster without buying hardware unless justified.

## Week 103 — AI incident assistant
Day 1: define bounded goal: summarize evidence and suggest hypotheses, never blindly execute remediation. Day 2: ingest Kubernetes events/log snippets/metrics/runbook references. Day 3: build prompt/context assembly and structured output: symptoms, evidence, likely causes, next checks. Day 4: test against known incidents such as ImagePullBackOff, selector mismatch, OOMKilled. Day 5: add safeguards: confidence, citations to evidence, no automatic destructive commands. Day 6: compare AI diagnosis with your own manual diagnosis and score accuracy. Day 7: document architecture, limitations, security, and demo scenario.

## Week 104 — Final FAANG readiness capstone
Day 1: clean repo, diagrams, README, runbooks, incidents, CI, IaC. Day 2: deploy platform from documented steps with minimal manual fixes. Day 3: run a reliability/load/observability demonstration. Day 4: unknown-failure incident drill and postmortem. Day 5: 45-minute system-design mock + 45-minute coding mock. Day 6: 60-minute portfolio/interview presentation covering architecture, tradeoffs, failures, AWS, Kubernetes, SRE and AI component. Day 7: final scorecard: Linux, networking, Python, Kubernetes, AWS/Terraform, SRE, distributed systems, coding, system design, behavioral. Identify gaps, begin applying/interviewing, and use real interview feedback to drive the next iteration.

# Graduation standard
You are finished with the curriculum only when you can independently build and operate the core platform, troubleshoot from evidence, explain tradeoffs without reading notes, and pass realistic coding/troubleshooting/system-design mocks. The portfolio should show not only successful deployments but also incident reports, runbooks, SLOs, diagrams, automation, and deliberate design decisions.
