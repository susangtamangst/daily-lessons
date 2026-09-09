# Two-Year FAANG SRE / Platform Engineering Roadmap

**Target:** Job-level readiness for SRE, Platform Engineer, Production Engineer, Systems Development Engineer, Cloud Infrastructure Engineer, and infrastructure-focused SWE roles.

**Cadence:** 1–2 hours/day. Each week follows: concepts → hands-on → deep dive → failure lab → automation → interview practice → review.

## Year 1 — Foundations to Production Kubernetes

1. Linux process model and shell fluency
2. Linux filesystems, permissions, users, services
3. Networking: IP, ports, TCP/UDP
4. DNS, routing, NAT, HTTP/TLS
5. Python fundamentals for operations
6. Python files, JSON, APIs, exceptions
7. Python testing, logging, packaging
8. Git and collaborative workflows
9. Containers: images, layers, registries
10. Dockerfiles, volumes, networks, debugging
11. Kubernetes architecture and kind
12. Pods, Deployments, ReplicaSets
13. Services, DNS, networking
14. ConfigMaps, Secrets, probes
15. Requests, limits, scheduling
16. Storage, PV/PVC, StatefulSets
17. Ingress and traffic routing
18. Kubernetes troubleshooting I
19. Kubernetes troubleshooting II
20. Helm and packaging
21. PostgreSQL fundamentals
22. Redis and caching
23. Application reliability patterns
24. Metrics with Prometheus
25. Dashboards with Grafana
26. Logging pipelines
27. OpenTelemetry and tracing
28. SLIs, SLOs, error budgets
29. Alerting and on-call fundamentals
30. Incident response and postmortems
31. GitHub Actions CI
32. Container security and supply chain
33. Argo CD and GitOps
34. GitOps environments and promotion
35. Terraform fundamentals
36. Terraform modules and state
37. AWS identity and IAM
38. AWS networking: VPC/subnets/routes
39. EC2, autoscaling, load balancers
40. S3, ECR, CloudWatch
41. RDS and managed databases
42. EKS architecture
43. Provision EKS with Terraform
44. Deploy platform stack to EKS
45. AWS/EKS troubleshooting
46. Reliability and disaster recovery
47. Cost awareness and capacity
48. Distributed systems fundamentals
49. Queues, async processing, backpressure
50. Caching, consistency, idempotency
51. System design foundations
52. Year 1 capstone and review

## Year 2 — Advanced Operations to Interview Readiness

53. Advanced Kubernetes scheduling
54. Autoscaling: HPA/VPA/cluster scaling
55. NetworkPolicy and zero-trust basics
56. Service mesh concepts
57. Kubernetes security hardening
58. RBAC and multi-tenancy
59. Policy as code
60. Secrets management
61. Advanced observability
62. Prometheus internals and cardinality
63. Tracing-driven debugging
64. Performance profiling
65. Load testing and capacity planning
66. Linux performance troubleshooting
67. Network performance troubleshooting
68. Database performance and failure modes
69. Distributed database concepts
70. Queues and stream processing
71. Kafka fundamentals
72. Event-driven architecture
73. Resilience patterns
74. Chaos engineering
75. Multi-region design
76. Disaster recovery drills
77. Platform engineering product mindset
78. Internal developer platforms
79. Backstage/platform APIs concepts
80. Golden paths and templates
81. Developer experience metrics
82. Advanced Terraform patterns
83. Module strategy / Terragrunt concepts
84. AWS Organizations and multi-account
85. Advanced EKS operations
86. Karpenter and node lifecycle
87. Cloud security and threat modeling
88. FinOps for platform engineers
89. Python automation project
90. Go awareness for infrastructure roles
91. DSA: arrays, strings, hash maps
92. DSA: stacks, queues, linked lists
93. DSA: trees, heaps, graphs
94. Coding interview patterns
95. System design: URL shortener
96. System design: metrics platform
97. System design: deployment platform
98. System design: log pipeline
99. Behavioral interview stories
100. Troubleshooting interview drills
101. AI infrastructure fundamentals
102. LLM serving and GPU scheduling concepts
103. AI incident assistant
104. Final FAANG readiness capstone

## Daily operating rhythm

Every week has seven lessons:

- **Day 1 — Concepts:** architecture, vocabulary, mental model, and failure model.
- **Day 2 — Build:** create the smallest working implementation.
- **Day 3 — Inspect:** inspect internals and explain how components interact.
- **Day 4 — Break:** inject a realistic failure and diagnose from evidence.
- **Day 5 — Automate:** codify the workflow using Python, shell, YAML, Terraform, or CI/CD.
- **Day 6 — Interview:** coding/troubleshooting/system-design/verbal explanation practice.
- **Day 7 — Review:** rebuild or explain from memory, update notes/runbooks, and pass a checkpoint.

That produces **728 daily lessons across 104 weeks**.

## Core portfolio project

The curriculum grows a single project rather than a collection of unrelated tutorials:

```text
faang-platform-lab/
├── apps/health-api/
├── kubernetes/
├── monitoring/
├── gitops/
├── terraform/
├── aws/
├── ai/
├── incidents/
├── runbooks/
├── system-design/
└── architecture/
```

The project evolves from a tiny Python API into a containerized, observable, GitOps-managed Kubernetes platform, then moves to AWS/EKS and ultimately includes an AI-assisted incident-triage service.

## Completion standard

A topic is not considered learned because it was deployed once. For each major topic, the student should be able to:

1. Explain the component and why it exists.
2. Build a minimal working version.
3. Diagnose at least one realistic failure without copying a tutorial.
4. Automate or codify the repeatable work.
5. Explain the tradeoffs verbally in an interview-style answer.
