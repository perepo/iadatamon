# iadatamon
Set of tools to monitorize and deploy Machine Learning Models on top of kubernetes

## Grafana
Based on the free version distributed by grafana, deploys on port 3000.
Check it at http://localhost:3000 user and password is admin.

## Prometheus
Deploy directly as helm chart
Add repos
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add kube-state-metrics https://kubernetes.github.io/kube-state-metrics
helm repo update
```
Install
```
# Helm 3
helm install [RELEASE_NAME] prometheus-community/prometheus
# Helm 2
helm install --name [RELEASE_NAME] prometheus-community/prometheus
```
