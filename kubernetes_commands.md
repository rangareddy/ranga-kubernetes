# Kubernetes Commands

## Kubernetes Cluster Info
```shell
kubectl version --short && \
kubectl get componentstatus && \
kubectl get nodes && \
kubectl cluster-info
```

## Resource Inspection
```shell
kubectl cluster-info
kubectl cluster-info dump --all-namespaces
kubectl describe node node01
kubectl describe deployment random-logger
kubectl describe deployments | grep "Replicas:"
kubectl get pods
```
## Events
```shell
kubectl get events
kubectl scale deployment/random-logger --replicas=2
kubectl get events --sort-by=.metadata.creationTimestamp
```
## Inspecting Containers
```shell
POD=$(kubectl get pod  -o jsonpath="{.items[0].metadata.name}")
kubectl exec $POD -- cat entrypoint.sh
kubectl exec -it $POD -- /bin/sh
kubectl exec $POD -- uptime
kubectl exec $POD -- ps
kubectl exec $POD -- stat -f /
kubectl exec $POD --container random-logger -- lsof
kubectl exec $POD --container random-logger -- iostat
kubectl exec $POD --container random-logger -- ls -a -l
```

