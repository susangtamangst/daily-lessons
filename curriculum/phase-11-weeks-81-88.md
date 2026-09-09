# Phase 11 — Weeks 81–88: Developer Experience, Advanced Terraform/AWS/EKS, Security, FinOps

## Week 81 — Developer experience metrics
Day 1: define deployment frequency, lead time, change failure rate, MTTR, platform adoption. Day 2: instrument one metric from GitHub/deploy history manually. Day 3: identify one bottleneck in service delivery. Day 4: test whether a platform change improves it. Day 5: avoid gaming vanity metrics. Day 6: interview drill on measuring platform value. Day 7: DX scorecard.

## Week 82 — Advanced Terraform patterns
Day 1: `for_each`, dynamic composition, dependency boundaries. Day 2: create multi-environment configuration without copy/paste. Day 3: module versioning and backwards compatibility. Day 4: refactor causing plan churn; stabilize resource addressing. Day 5: test/validate/lint IaC. Day 6: interview drill on state and refactors. Day 7: module review checklist.

## Week 83 — Module strategy / Terragrunt concepts
Day 1: repo layout and environment composition. Day 2: DRY vs explicit tradeoff. Day 3: remote-state dependency patterns. Day 4: circular/deep abstraction anti-pattern exercise. Day 5: evaluate Terragrunt-style orchestration without adopting blindly. Day 6: design discussion on module ownership. Day 7: document chosen IaC architecture.

## Week 84 — AWS Organizations and multi-account
Day 1: account boundaries and Organizations concepts. Day 2: dev/stage/prod account model. Day 3: cross-account role assumptions conceptually. Day 4: SCP vs IAM policy reasoning exercise. Day 5: centralized logging/network/security patterns. Day 6: interview drill on blast-radius reduction. Day 7: multi-account diagram.

## Week 85 — Advanced EKS operations
Day 1: version upgrades and compatibility planning. Day 2: node group upgrades/draining. Day 3: PDBs and safe maintenance. Day 4: simulate drain and observe workload availability. Day 5: add-on lifecycle strategy. Day 6: interview drill on zero/low-downtime cluster upgrades. Day 7: upgrade runbook.

## Week 86 — Karpenter and node lifecycle
Day 1: dynamic node provisioning concepts. Day 2: compare managed node groups vs Karpenter. Day 3: constraints, instance selection, disruption. Day 4: failure/tabletop for unschedulable workload/node consolidation. Day 5: cost/capacity tradeoffs. Day 6: explain scaling path from Pending Pod to new node. Day 7: architecture decision record.

## Week 87 — Cloud security and threat modeling
Day 1: assets, trust boundaries, threats. Day 2: threat-model your platform request path. Day 3: IAM/network/secret risks. Day 4: misconfiguration scenario and mitigation. Day 5: logging/detection requirements. Day 6: interview drill on shared responsibility. Day 7: threat model document with prioritized controls.

## Week 88 — FinOps for platform engineers
Day 1: unit economics and major cloud cost drivers. Day 2: compare on-demand/reserved/spot concepts. Day 3: storage/network/NAT/LB cost review. Day 4: find waste in hypothetical architecture. Day 5: define cost guardrails/budgets. Day 6: interview drill on cost vs availability. Day 7: phase checkpoint with cost-optimized architecture and explicit tradeoffs.
