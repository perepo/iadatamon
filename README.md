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
helm repo update
```
Install operator and stack. More info at https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack#kube-prometheus-stack
```
# Helm 3
helm install [RELEASE_NAME] prometheus-community/kube-prometheus-stack
```

Depending on the platform an error with the hostRootFsMount / mount may arise
This piece of code path the daemon set to remove mount propagation
```
 kubectl patch ds prometheus-node-exporter --type "json" -p '[{"op": "remove", "path" : "/spec/template/spec/containers/0/volumeMounts/2/mountPropagation"}]'
  ```
  
 continue reading https://www.infracloud.io/blogs/prometheus-operator-helm-guide/
