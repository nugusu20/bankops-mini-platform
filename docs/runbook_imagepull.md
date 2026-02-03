# Runbook: ErrImagePull / ImagePullBackOff (kind)

## Symptom
Pod status shows: ErrImagePull / ImagePullBackOff

## Root cause (common in kind)
The image tag exists locally on the host, but the kind node cannot see it.
Kubernetes tries to pull it from a remote registry and fails.

## Fix
1) Load the local image into the kind cluster:
   kind load docker-image bankops-api:0.1 --name bankops

2) Restart the deployment to recreate pods:
   kubectl rollout restart deployment/bankops-api

## Verify
kubectl get pods
kubectl port-forward svc/bankops-api 8080:8080
curl http://localhost:8080/health
