# Cluster: local

The local kind cluster used for learning and development.

## Entrypoint

root-app.yaml (added later) is the app-of-apps.
It points ArgoCD at the sibling folders in this repo:
- infrastructure/
- observability/
- apps/
