# ArgoCD Bootstrap

The one thing GitOps can't manage: ArgoCD itself.

## Recovery procedure (if cluster is lost)

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

Then apply the root app from clusters/local/.
Everything else rebuilds automatically.
