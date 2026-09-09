# Phase 5 — Weeks 33–40: GitOps, Terraform, AWS Core

## Week 33 — Argo CD and GitOps
Day 1: learn Git as desired-state source, pull-based reconciliation, drift. Day 2: install Argo CD locally and register repo/cluster. Day 3: deploy health API from Git. Day 4: manually mutate a Deployment and observe drift/self-heal behavior. Day 5: separate app source from deployment configuration conceptually. Day 6: interview drill on GitOps vs CI push deploy. Day 7: rebuild deployment flow from clean cluster.

## Week 34 — Environments and promotion
Day 1: create dev/stage/prod-like overlays or values. Day 2: promote an image tag through environments by PR. Day 3: add environment-specific replicas/resources/config. Day 4: break promotion with bad config and roll back through Git. Day 5: document change-control and rollback strategy. Day 6: explain progressive delivery/canary concepts. Day 7: demo Git commit → Argo reconciliation → healthy workload.

## Week 35 — Terraform fundamentals
Day 1: provider/resource/data/source/state/plan/apply/destroy. Day 2: provision simple local or AWS sandbox resource. Day 3: variables, outputs, locals. Day 4: change resource and inspect plan before apply. Day 5: import/state inspection concept; never hand-edit state casually. Day 6: interview drill on declarative IaC and idempotence. Day 7: recreate small stack from empty state.

## Week 36 — Terraform modules and state
Day 1: refactor repeated configuration into module. Day 2: module inputs/outputs. Day 3: remote state and locking concepts. Day 4: failure lab for configuration/state drift and safe recovery. Day 5: lifecycle/meta-arguments (`for_each`, `count`, dependencies) with small exercises. Day 6: explain module boundaries and versioning. Day 7: publish reusable network/module skeleton.

## Week 37 — AWS identity and IAM
Day 1: account, IAM user, role, policy, principal. Day 2: inspect AWS CLI identity and configure least-privilege sandbox credentials safely. Day 3: identity-based vs resource-based policy concepts. Day 4: deny/allow troubleshooting exercise using policy evaluation logic. Day 5: roles and temporary credentials; explain why static keys are risky. Day 6: interview drill on least privilege and cross-account access. Day 7: write IAM security checklist.

## Week 38 — VPC, subnets, routes
Day 1: VPC/CIDR/subnet map. Day 2: public vs private subnet and route tables. Day 3: IGW vs NAT Gateway purpose. Day 4: failure lab: route missing → instance cannot reach target; reason from route table. Day 5: security group vs NACL. Day 6: whiteboard VPC with 2 AZs/public+private subnets. Day 7: Terraform the network design and validate plan.

## Week 39 — EC2, autoscaling, load balancers
Day 1: EC2 lifecycle, AMI, instance type, userdata. Day 2: launch disposable instance and serve HTTP. Day 3: ALB target group/health checks. Day 4: failure lab: bad SG or unhealthy target; diagnose from layers. Day 5: Auto Scaling Group desired/min/max and replacement behavior. Day 6: interview drill on horizontal scaling and failure domains. Day 7: document request flow Internet → ALB → instance.

## Week 40 — S3, ECR, CloudWatch
Day 1: S3 object model, bucket policy, lifecycle/versioning. Day 2: push project image to ECR. Day 3: CloudWatch metrics/logs/alarms basics. Day 4: permissions failure lab for ECR/S3. Day 5: lifecycle/cost hygiene and cleanup automation. Day 6: explain managed service tradeoffs. Day 7: phase checkpoint: Terraform network + compute/container registry basics and teardown safely.
