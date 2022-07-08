# Grafana helm values repo

This repo is used by ArgoCD to deploy Grafana in the `shared.k8s.local` Kubernetes cluster.

## Upgrade with ArgoCD

Go to https://argocd.nuglif.net/applications?proj=arcadia&sync=&health=&namespace=&cluster=&labels=app%253Dgrafana

## Manually upgrade the chart

```
helm dependency build
helm template grafana . -f values-global.yaml -f values-shared.yaml > manifests.yaml
kubectl --context shared.k8.local -n monitoring apply -f manifests.yaml
```

