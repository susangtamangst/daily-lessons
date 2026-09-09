# Phase 6 — Weeks 41–48: RDS, EKS, Reliability, Distributed Systems

## Week 41 — RDS and managed databases
Day 1: RDS concepts, engine, subnet group, SG, backups, Multi-AZ. Day 2: provision small PostgreSQL RDS in private subnets. Day 3: connect from approved compute only. Day 4: failure lab with blocked SG/wrong DNS/credential and layer-by-layer diagnosis. Day 5: backups, snapshots, maintenance windows, parameter groups. Day 6: interview drill: RDS vs self-managed DB. Day 7: Terraform and teardown safely.

## Week 42 — EKS architecture
Day 1: managed control plane vs worker nodes. Day 2: node groups, IAM roles, CNI, kube-proxy, CoreDNS. Day 3: cluster authentication/authorization path. Day 4: compare kind architecture to EKS. Day 5: estimate cost components before provisioning. Day 6: explain EKS request and workload path. Day 7: architecture diagram and preflight checklist.

## Week 43 — Provision EKS with Terraform
Day 1: module/design plan and state strategy. Day 2: create VPC/subnets/IAM. Day 3: create EKS control plane/node group. Day 4: connect `kubectl` and verify nodes/system Pods. Day 5: failure lab: node join/IAM/network issue and evidence-based diagnosis. Day 6: explain Terraform dependency graph and EKS bootstrap. Day 7: destroy/recreate selected components safely.

## Week 44 — Deploy platform stack to EKS
Day 1: push app image to ECR. Day 2: deploy via GitOps/Helm. Day 3: expose with AWS load balancer pattern. Day 4: add config/secrets/resources/probes. Day 5: connect managed DB carefully. Day 6: compare local kind vs EKS differences. Day 7: demo end-to-end public request with observability.

## Week 45 — AWS/EKS troubleshooting
Day 1: establish triage layers: AWS network/IAM → EKS control plane → node → Pod → Service → app. Day 2: ImagePull failure from ECR permission. Day 3: unhealthy load-balancer target. Day 4: DNS/service failure. Day 5: node NotReady/Pending scheduling drill. Day 6: timed interview incident. Day 7: write two cloud incident reports.

## Week 46 — Reliability and disaster recovery
Day 1: RTO/RPO, backup vs replication. Day 2: simulate Pod/node loss and observe recovery. Day 3: database backup/restore tabletop. Day 4: AZ failure design exercise. Day 5: create recovery runbook and test one step. Day 6: interview drill on designing for failure. Day 7: DR review with measurable objectives.

## Week 47 — Cost awareness and capacity
Day 1: identify cost drivers: compute, control plane, LB, NAT, storage, data transfer. Day 2: right-size requests and node capacity. Day 3: estimate monthly lab architecture cost. Day 4: find one intentionally wasteful design and reduce cost without hurting SLO. Day 5: tagging/budget/alarm concepts. Day 6: discuss cost vs reliability tradeoffs. Day 7: produce one-page cost model.

## Week 48 — Distributed systems fundamentals
Day 1: partial failure, latency, unreliable networks. Day 2: consistency vs availability concepts without slogan memorization. Day 3: replication leader/follower concepts. Day 4: failure lab/tabletop: dependency partition and stale reads. Day 5: timeouts/retries/idempotency revisited across services. Day 6: interview drill on why distributed systems are harder than one process. Day 7: phase checkpoint: explain entire platform and three failure paths from client to data.
