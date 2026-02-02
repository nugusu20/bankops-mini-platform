#bankops-mini-plaform

A small "real-world" DevOps lab that simulates an enterprise GitOps workflow:
Git -> (ArgoCD) -> (OpenShift/Kubernetes) -> Services + Health + Runbooks

## Repo structure (high level)
- services/  : application code (api, web)
- apps/      : Kubernetes/OpenShift manifests per service
- platform/  : shared platform resources (RBAC, namespaces, secrets, policies)
- argocd/    : ArgoCD applications (GitOps)
- scripts/   : troubleshooting / health / rollback helpers
- docs/      : architecture + runbooks + incident drills

