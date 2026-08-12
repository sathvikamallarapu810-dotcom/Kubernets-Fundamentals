Kubernetes Day 1 — Cluster Fundamentals & Pod Deployment

As part of my Cloud & DevOps Engineering learning roadmap, I started learning Kubernetes with a focus on understanding cluster architecture, core components, and workload deployment.

Overview

Kubernetes is a container orchestration platform used to automate the deployment, scaling, networking, and management of containerized applications.

For the first day, I focused on understanding the basic Kubernetes architecture and deploying my first workload using Minikube.

Objectives
Understand Kubernetes and its role in container orchestration
Learn the basic Kubernetes cluster architecture
Understand Control Plane and Node responsibilities
Learn the concept of Pods
Understand the role of the Scheduler and Kubelet
Set up and verify a local Kubernetes cluster using Minikube
Deploy an Nginx container as a Kubernetes Pod
Practice essential kubectl commands
Kubernetes Architecture

The basic workflow I learned:

                    Kubernetes Cluster
                           │
                 ┌─────────┴─────────┐
                 │                   │
            Control Plane          Node
                 │                   │
        ┌────────┼────────┐          │
        │        │        │          │
    API Server Scheduler  etc.      Pod
                                      │
                                  Container
                                      │
                                    Nginx
Key Components
Component	Responsibility
API Server	Entry point for Kubernetes API requests
Scheduler	Selects a suitable node for new Pods
Kubelet	Ensures containers described by Pods are running
Control Plane	Manages and maintains the cluster state
Node	Provides compute resources for workloads
Pod	Smallest deployable unit in Kubernetes
CoreDNS	Provides DNS-based service discovery inside the cluster
Environment
OS: Windows
Kubernetes: v1.34.0
Cluster: Minikube
Container Runtime: Docker
Workload: Nginx
CLI: kubectl
Hands-on Implementation
1. Verify Kubernetes Cluster
kubectl cluster-info

This verified that the Kubernetes control plane and CoreDNS service were running successfully.

2. Check Cluster Nodes
kubectl get nodes

Result:

NAME       STATUS   ROLES           VERSION
minikube   Ready    control-plane   v1.34.0

The Ready status confirms that the Minikube node is healthy and able to run workloads.

3. Deploy an Nginx Pod
kubectl run nginx-pod --image=nginx
4. Verify the Pod
kubectl get pods

Result:

NAME        READY   STATUS    RESTARTS
nginx-pod   1/1     Running   0
Deployment Flow
kubectl
   │
   ▼
Kubernetes API Server
   │
   ▼
Scheduler
   │
   ▼
Minikube Node
   │
   ▼
nginx-pod
   │
   ▼
Nginx Container
Key Learnings
Pod

A Pod is the smallest deployable unit in Kubernetes.

A Pod can contain one or more containers that share networking and storage resources.

Scheduler

The Scheduler determines which available node should run a newly created Pod based on cluster requirements and available resources.

Kubelet

The Kubelet runs on each node and is responsible for ensuring that the containers defined in Pods are running and healthy.

Commands Practiced
kubectl cluster-info
kubectl get nodes
kubectl run nginx-pod --image=nginx
kubectl get pods
Verification

The Kubernetes environment was successfully verified:

Control Plane    → Running
Minikube Node    → Ready
Nginx Pod        → Running
Container        → 1/1 Ready
Restarts         → 0
Progress
Cloud & DevOps Roadmap

AWS Foundations       ✅
Linux & Networking    ✅
Git & GitHub          ✅
Docker                ✅
Docker Compose        ✅
Docker Networking     ✅
Docker Hub            ✅
Docker Capstone       ✅
────────────────────────────
Kubernetes Day 1      ✅
