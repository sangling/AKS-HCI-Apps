**Use Grafana with AKS-HCI**

[Grafana](https://github.com/grafana/grafana) is a tool used to view, query, and visualize metrics on the Grafana dashboards. It can be configured to use Prometheus as the data source. The deployment guidance below requires that you license your own copy of Grafana.
 

**Grafana dashboards available in AKS-HCI**

Following Grafana dashboards are supported in AKS-HCI.

- API server
- Networking / Cluster
- Compute Resources / Cluster
- Compute Resources / Namespace (Pods)
- Compute Resources / Node (Pods)
- Compute Resources / Pod
- Compute Resources / Workload
- Compute Resources / Namespace (Workloads)
- Kubelet
- Networking / Namespace (Pods)
- Networking / Namespace (Workload)
- Persistent Volumes
- Networking / Pod
- StatefulSets
- Networking / Workload
- Compute Resources / Cluster (Windows)
- Compute Resources / Namespace (Windows Pods)
- Compute Resources / Pod (Windows)
- USE Method / Cluster (Windows)
- USE Method / Node (Windows)



**Deploy Grafana**

There are two approaches for deploying Granafa for AKS-HCI.

 

***Deploy Grafana in AKS-HCI cluster***

Grafana can be installed using helm chart

```
helm repo add grafana https://grafana.github.io/helm-charts

helm repo update

helm install grafana grafana/grafana --set nodeSelector."kubernetes.io/os"=linux --set sidecar.dashboards.enabled=true --set sidecar.datasources.enabled=true -n monitoring


```

 

***Deploy Grafana outside AKS-HCI cluster***