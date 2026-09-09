# Phase 2 — Weeks 9–16: Containers and Core Kubernetes

## Week 9 — Container images, layers, registries
**Day 1.** Learn image vs container, OCI image idea, layers, registry. Inspect local images with `docker image ls` and `docker history`.
**Day 2.** Pull and run `nginx`; compare image metadata with running container metadata. Exit: explain immutable image vs mutable runtime state.
**Day 3.** Build a minimal image for your Python health API. Understand `FROM`, `WORKDIR`, `COPY`, `RUN`, `CMD`.
**Day 4.** Failure lab: wrong `CMD` and missing file. Diagnose with `docker ps -a`, `docker logs`, `docker inspect`.
**Day 5.** Tagging and registries. Tag an image with semantic version and `latest`; explain why production should avoid relying on mutable tags.
**Day 6.** Interview drill: “What happens when Docker runs an image?” Explain namespaces/cgroups conceptually, filesystem layers, process start.
**Day 7.** Rebuild the image from scratch and document image → container → process flow.

## Week 10 — Dockerfiles, volumes, networks, debugging
**Day 1.** Improve Dockerfile ordering and cache use. Compare rebuild time before/after moving dependency installation earlier.
**Day 2.** Learn bind mounts vs named volumes. Persist a file across container recreation.
**Day 3.** Learn Docker bridge networking and container DNS. Run app + another container and connect by container name/network.
**Day 4.** Failure lab: wrong exposed/listening port. Use logs, `docker inspect`, `ss`, and `curl` to isolate mismatch.
**Day 5.** Add healthcheck and non-root user to image. Explain operational and security benefits.
**Day 6.** Interview drill: image size, multi-stage builds, secrets, PID 1, signals.
**Day 7.** Phase lab: containerize health API cleanly; run, inspect, stop, remove, rebuild without notes.

## Week 11 — Kubernetes architecture and kind
**Day 1.** Create 3-node kind cluster. Learn API server, scheduler, controller manager, etcd, kubelet, container runtime.
**Day 2.** Inspect nodes and system Pods with `kubectl get nodes -o wide`, `kubectl get pods -A`, `docker ps`.
**Day 3.** Trace `kubectl` → API server → desired state → scheduler → kubelet → container runtime.
**Day 4.** Failure lab: create bad-image Pod; diagnose `ImagePullBackOff` with `kubectl describe` and Events.
**Day 5.** Learn namespaces and contexts. Create `platform-lab` namespace and set it in a context.
**Day 6.** Interview drill: “What happens when you submit a Pod?” Explain in sequence.
**Day 7.** Recreate cluster and basic Pod from memory; write architecture diagram.

## Week 12 — Pods, Deployments, ReplicaSets
**Day 1.** Create standalone Pod and inspect lifecycle/status/events.
**Day 2.** Create Deployment with 3 replicas. Inspect Deployment → ReplicaSet → Pods ownership.
**Day 3.** Delete one managed Pod and observe reconciliation. Explain desired vs actual state.
**Day 4.** Failure lab: bad image in Deployment, use rollout status/history/describe to find issue.
**Day 5.** Update image and perform rollout + rollback. Record what changes in ReplicaSets.
**Day 6.** Interview drill: Pod vs Deployment vs ReplicaSet; when not to create bare Pods.
**Day 7.** Build `kubernetes/base/deployment.yaml` for health API without imperative helper commands.

## Week 13 — Services, DNS, networking
**Day 1.** Learn ClusterIP Service and selectors. Expose health API internally.
**Day 2.** Inspect Service, EndpointSlice/endpoints and match them to Pod IPs.
**Day 3.** Launch debug Pod and resolve Service DNS; test service name and FQDN.
**Day 4.** Failure lab: intentionally wrong selector so Service has no endpoints; diagnose from Service → endpoints → Pods.
**Day 5.** Learn `port` vs `targetPort`; deliberately mismatch then fix.
**Day 6.** Interview drill: explain how traffic reaches a Pod through a Service.
**Day 7.** Write networking runbook: DNS → Service → EndpointSlice → Pod IP → container port.

## Week 14 — ConfigMaps, Secrets, probes
**Day 1.** Move app config to ConfigMap via environment variables.
**Day 2.** Create Secret for mock credential; mount/inject safely. Never commit real secrets.
**Day 3.** Implement `/health` and `/ready`; configure liveness/readiness probes and observe probe events.
**Day 4.** Failure lab: make readiness fail while process stays alive; observe Service stop routing to unready Pod.
**Day 5.** Learn startup probe purpose and when liveness can cause restart loops.
**Day 6.** Interview drill: liveness vs readiness vs startup probe with real failure examples.
**Day 7.** Add ConfigMap, Secret example, and probes to manifests; document safe secret handling.

## Week 15 — Requests, limits, scheduling
**Day 1.** Learn CPU/memory requests vs limits and QoS basics.
**Day 2.** Add requests/limits to API; inspect `kubectl describe pod` and node allocation.
**Day 3.** Learn scheduler inputs: resource fit, affinity, taints/tolerations conceptually.
**Day 4.** Failure lab: request more CPU/memory than nodes can provide; diagnose Pending Pod from Events.
**Day 5.** Trigger memory limit failure in a controlled test container and observe `OOMKilled`.
**Day 6.** Interview drill: why requests are for scheduling and limits are runtime constraints.
**Day 7.** Write resource-sizing notes from evidence rather than arbitrary values.

## Week 16 — Storage, PV/PVC, StatefulSets
**Day 1.** Learn ephemeral container filesystem vs persistent volume concepts.
**Day 2.** Create PVC and mount it into a Pod; write data, recreate Pod, confirm persistence.
**Day 3.** Learn PV/PVC/StorageClass binding flow and dynamic provisioning conceptually.
**Day 4.** Failure lab: PVC Pending; inspect claim, StorageClass and events.
**Day 5.** Learn StatefulSet identity and stable storage; deploy a small stateful example.
**Day 6.** Interview drill: Deployment vs StatefulSet and why databases need special treatment.
**Day 7.** Phase checkpoint: deploy API with config, probes, resources, Service and persistent demo storage; explain every object.
