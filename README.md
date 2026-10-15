# gitops-infra

GitOps-managed Kubernetes infrastructure using **ArgoCD**.

## Philosophy

> Git is the single source of truth.
> ArgoCD syncs the cluster to match this repo.
> No manual `kubectl apply` for anything committed here.

## Structure

| Path | Purpose |
|------|---------|
| `bootstrap/` | One-time ArgoCD install manifests |
| `clusters/<name>/` | Per-cluster entrypoints (app-of-apps) |
| `infrastructure/` | Cluster add-ons (ingress, cert-manager, etc.) |
| `observability/` | Prometheus, Grafana, alerts |
| `apps/` | Application workloads |

## How it works

1. Install ArgoCD manually (see `bootstrap/`).
2. Apply the root app from `clusters/local/`.
3. ArgoCD reads the rest of this repo and reconciles the cluster.
