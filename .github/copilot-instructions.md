# Copilot Instructions for lab

## Repository Overview

This is an exploratory lab repository for Kubernetes configurations and deployments. It contains various examples and experiments for learning and testing Kubernetes concepts.

## Repository Structure

- **`deployment/`** - Kubernetes deployment examples (nginx, httpd, rolling updates)
- **`k8s/`** - Basic Kubernetes resource examples
- **`mealie/`** - Complete application deployment (Mealie recipe manager with persistent storage)
- **`helm/`** - Helm chart configurations
- **`.userhome/`** - Environment setup and convenience settings

## Key Conventions

### Kubernetes Resources

- **Naming pattern**: Resource names match their app label (e.g., `name: mealie` with `app: mealie`)
- **Namespaces**: Applications like Mealie use dedicated namespaces declared in `namespace.yaml`
- **Deployment strategies**: Examples include both `RollingUpdate` (with `maxUnavailable: 1`, `maxSurge: 1`) and `Recreate` strategies
- **Replica counts**: Test deployments typically use 10 replicas, production-like apps (Mealie) use 1

### Storage Pattern

For applications requiring persistent storage (see `mealie/`):
1. Define `PersistentVolumeClaim` in `storage.yaml`
2. Reference in deployment via `volumeMounts` and `volumes`
3. Standard mount path: `/app/data`

### Service Exposure

Services follow the pattern in `mealie/service.yaml`:
- Type: `NodePort`
- Target port matches container port
- NodePort typically in 30000+ range

## kubectl Shortcuts

This repo uses `k` as a shortcut for `kubectl` (defined in `.userhome/README.md`).

When generating commands or examples, use the full `kubectl` command for clarity.

## Generating Resources

Use `kubectl --dry-run=client -o yaml` to generate resource templates:

```bash
kubectl run nginx-yaml --image=nginx --dry-run=client -o yaml > nginx.yaml
kubectl create -f nginx.yaml
```
