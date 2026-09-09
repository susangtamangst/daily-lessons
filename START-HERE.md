# Start Here — FAANG Platform Engineering Daily Curriculum

This repository is designed so you can follow the curriculum without returning to ChatGPT for a daily lesson.

## How to use it

- Study **60–120 minutes per day**.
- Follow the weeks in order unless you already have strong evidence that you can pass that week's checkpoint.
- Do not mark a topic complete just because a command worked once.
- For every major topic, be able to **explain it, build it, break it, troubleshoot it, automate it, and discuss tradeoffs**.
- Keep your implementation, incident reports, runbooks and diagrams in a separate evolving project repo such as `faang-platform-lab`.

## Curriculum

1. [Weeks 1–8 — Linux, Networking, Python, Git](curriculum/phase-01-weeks-01-08.md)
2. [Weeks 9–16 — Containers and Core Kubernetes](curriculum/phase-02-weeks-09-16.md)
3. [Weeks 17–24 — Kubernetes Operations, Data, Reliability, Prometheus](curriculum/phase-03-weeks-17-24.md)
4. [Weeks 25–32 — Grafana, Logs, Traces, SRE, CI, Security](curriculum/phase-04-weeks-25-32.md)
5. [Weeks 33–40 — GitOps, Terraform, AWS Core](curriculum/phase-05-weeks-33-40.md)
6. [Weeks 41–48 — RDS, EKS, Reliability, Distributed Systems](curriculum/phase-06-weeks-41-48.md)
7. [Weeks 49–56 — Async Systems, System Design, Advanced Kubernetes](curriculum/phase-07-weeks-49-56.md)
8. [Weeks 57–64 — Kubernetes Security and Advanced Observability](curriculum/phase-08-weeks-57-64.md)
9. [Weeks 65–72 — Performance, Databases, Kafka, Events](curriculum/phase-09-weeks-65-72.md)
10. [Weeks 73–80 — Resilience, Chaos, Multi-Region, Platform Engineering](curriculum/phase-10-weeks-73-80.md)
11. [Weeks 81–88 — Developer Experience, Advanced Terraform/AWS/EKS](curriculum/phase-11-weeks-81-88.md)
12. [Weeks 89–96 — Automation, DSA, Coding, System Design](curriculum/phase-12-weeks-89-96.md)
13. [Weeks 97–104 — Platform Design, AI Infrastructure, Final Capstone](curriculum/phase-13-weeks-97-104.md)

The original high-level overview remains in [ROADMAP.md](ROADMAP.md).

## Weekly rhythm

Each week intentionally progresses through a combination of:

1. Learn the mental model.
2. Build the smallest working implementation.
3. Inspect what is happening internally.
4. Break something intentionally.
5. Troubleshoot from evidence rather than guessing.
6. Practice explaining or solving it under interview conditions.
7. Review/rebuild and produce a durable artifact such as a runbook, incident report, design note or code change.

## Portfolio evidence to accumulate

By the end, your portfolio should contain application code, Docker/container configuration, Kubernetes manifests/Helm, GitOps configuration, Terraform/AWS/EKS infrastructure, dashboards, SLOs, incident reports, runbooks, architecture diagrams, system-design exercises, CI/CD, security decisions, and an AI-assisted incident-triage component.

## Important

Cloud services can incur charges. For AWS/EKS lessons, create only resources you understand, set budgets/alerts, and destroy lab resources when finished. Use the local kind lab whenever the learning objective does not require a managed cloud service.
