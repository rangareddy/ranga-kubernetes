# Kubernetes Commands

## Kubernetes Cluster Info
```shell
kubectl version --short && \
kubectl get componentstatus && \
kubectl get nodes && \
kubectl cluster-info
```

## Resource Inspection
```
kubectl cluster-info
kubectl cluster-info dump --all-namespaces
kubectl describe node node01
kubectl describe deployment random-logger
kubectl describe deployments | grep "Replicas:"
kubectl get pods
```


