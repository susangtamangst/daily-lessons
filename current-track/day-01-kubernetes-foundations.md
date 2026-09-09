# Day 1 — Kubernetes Foundations with kind

**Time:** 60–90 minutes  
**Environment:** Windows + WSL2 + Docker Desktop + kind + kubectl  
**Laptop target:** 4 CPU / 16 GB RAM

## Goal

Build a lightweight three-node Kubernetes cluster locally and understand what a cluster, control plane, worker node, Pod, scheduler, kubelet, and reconciliation loop are.

By the end of the lesson, you should be able to explain what happens between running a Kubernetes command and a container process running on a node.

## Why this matters

Platform/SRE interviews rarely care that you memorized `kubectl` commands. They care whether you understand the layers underneath them and can diagnose failures from evidence.

The lab deliberately uses `kind` because it gives us real Kubernetes while remaining light enough for a 4-core/16-GB laptop.

## Mental model

```text
Windows laptop
    |
    v
Docker Desktop / WSL2
    |
    v
kind
    |
    v
Kubernetes cluster
    |
    +-- control-plane node
    +-- worker node
    +-- worker node
```

With kind, each Kubernetes **node is itself a container**. Kubernetes then runs workload containers inside those nodes.

Do not confuse:

- the container representing a kind node
- the application container running inside a Kubernetes Pod

They are different layers.

## Core Kubernetes architecture

```text
kubectl
   |
   v
API Server
   |
   +--> etcd
   |
   +--> Scheduler
   |
   +--> Controllers
             |
             v
          Worker Node
             |
           kubelet
             |
      container runtime
             |
             v
            Pod
```

### API server

The front door of the Kubernetes control plane. `kubectl` sends API requests; it does not directly manipulate worker nodes.

### Scheduler

Chooses an appropriate node for a Pod that has not yet been assigned to one.

### Controllers

Continuously compare **desired state** with **actual state** and work to reconcile the difference.

Example:

```text
Desired replicas: 3
Actual replicas: 2
```

A controller works toward restoring the missing replica.

### etcd

The distributed key-value store containing Kubernetes cluster state.

### kubelet

The node agent responsible for ensuring the Pods assigned to its node are running as declared.

## Part 1 — Verify tools

Run in PowerShell:

```powershell
docker version
kubectl version --client
kind version
wsl -l -v
```

Do not proceed until Docker, kubectl, and kind respond successfully.

## Part 2 — Create the lab repository locally

```powershell
mkdir faang-platform-lab
cd faang-platform-lab
git init
mkdir kubernetes
```

Create `kubernetes/kind-config.yaml`:

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
  - role: control-plane
  - role: worker
  - role: worker
```

## Part 3 — Create the cluster

```powershell
kind create cluster --name faang-lab --config kubernetes/kind-config.yaml
```

Verify:

```powershell
kubectl get nodes
kubectl get nodes -o wide
```

Expected conceptually:

```text
faang-lab-control-plane   Ready   control-plane
faang-lab-worker          Ready   <none>
faang-lab-worker2         Ready   <none>
```

### Inspect what kind created

```powershell
docker ps
```

You should see three containers corresponding to the three Kubernetes nodes.

## Part 4 — Inspect Kubernetes itself

```powershell
kubectl cluster-info
kubectl get namespaces
kubectl get pods -A
```

Look for components such as:

- `kube-apiserver`
- `kube-scheduler`
- `kube-controller-manager`
- `etcd`
- `coredns`
- `kube-proxy`

Do not memorize every flag. Identify which responsibility each component has.

## Part 5 — Create a standalone Pod

Use nginx only as a disposable workload for learning mechanics:

```powershell
kubectl run nginx --image=nginx
kubectl get pods
kubectl get pods -o wide
```

Look at the `NODE` column. You did not manually select that node; Kubernetes scheduling made the placement decision.

Inspect the Pod:

```powershell
kubectl describe pod nginx
```

Focus on:

- Node
- Image
- Status
- IP
- Events

The event flow should help you form this mental sequence:

```text
request submitted
    -> API server accepts it
    -> scheduler chooses node
    -> kubelet sees assignment
    -> image becomes available
    -> container starts
    -> Pod reaches Running
```

## Part 6 — Look inside the workload

```powershell
kubectl exec -it nginx -- sh
```

Inside:

```sh
ps
hostname
exit
```

Connect this to the Linux model:

```text
Kubernetes Pod
   -> container
      -> Linux process
```

## Part 7 — Observe Pod networking

```powershell
kubectl get pod nginx -o wide
```

Notice that the Pod has an IP.

For now simply recognize:

```text
Laptop IP != Node IP != Pod IP
```

Networking internals come later.

## Failure Lab 1 — Delete the standalone Pod

```powershell
kubectl delete pod nginx
kubectl get pods
```

The Pod should disappear and **not return**.

### Question

Why did Kubernetes not recreate it?

Because we created only a standalone Pod. There is no higher-level controller declaring that one nginx replica must continuously exist.

This sets up the next lesson on Deployments and reconciliation.

## Failure Lab 2 — ImagePullBackOff

Create a workload using a nonexistent image tag:

```powershell
kubectl run broken-app --image=nginx:this-tag-does-not-exist
kubectl get pods
```

Eventually it should fail with an image-pull-related status such as `ErrImagePull` or `ImagePullBackOff`.

Do not immediately delete it.

Collect evidence:

```powershell
kubectl describe pod broken-app
```

Read the **Events** section and answer:

1. What was Kubernetes attempting?
2. Which stage failed?
3. Is this a scheduler problem?
4. Is the application process even running yet?
5. What evidence identifies the image as the problem?

Then clean up:

```powershell
kubectl delete pod broken-app
```

## Troubleshooting habit

Before changing configuration, collect evidence.

For Pods, start with:

```text
kubectl get pods
        |
        v
kubectl get pod <name> -o wide
        |
        v
kubectl describe pod <name>
        |
        v
Events / status / node / image
        |
        v
kubectl logs <name>   (when an application process actually started)
```

## Interview practice

Answer out loud:

> What happens when a Pod is created in Kubernetes?

A strong beginner answer should mention the API server, scheduling, node assignment, kubelet, container runtime, and Pod lifecycle without pretending every implementation detail is identical across all clusters.

Then answer:

> Why would deleting a standalone Pod behave differently from deleting a Pod managed by a Deployment?

The key concept is **desired state and reconciliation**.

## Knowledge check

Without looking above:

1. What is a Kubernetes node?
2. What are our kind nodes physically implemented as?
3. Which component selects a node for an unscheduled Pod?
4. What role does kubelet play?
5. Why did the manually-created nginx Pod not return after deletion?
6. What is reconciliation?
7. Where would you first look when a Pod reports `ImagePullBackOff`?

## Definition of done

You are finished only when you can demonstrate and explain:

- [ ] Three Kubernetes nodes are `Ready`.
- [ ] You can identify control-plane and worker nodes.
- [ ] You can see the kind node containers with Docker.
- [ ] You can locate Kubernetes system Pods.
- [ ] You can show which node scheduled your nginx Pod.
- [ ] You can find Pod events with `kubectl describe`.
- [ ] You understand why a standalone Pod does not self-recreate.
- [ ] You diagnosed an intentional `ImagePullBackOff` from evidence.
- [ ] You can explain the API server → scheduler → kubelet → container flow aloud.

## Next lesson

**Day 2 — Deployments, ReplicaSets, desired state, and reconciliation.**

We will create multiple replicas, delete one, and prove why Kubernetes restores it automatically.
