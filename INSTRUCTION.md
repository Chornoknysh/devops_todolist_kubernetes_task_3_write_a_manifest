# Instructions to Deploy ToDo App on Kubernetes

### 1. Apply Namespace
```bash

kubectl apply -f .infrastructure/namespace.yml
Deploy Busybox Pod
kubectl apply -f .infrastructure/busybox.yml
Deploy ToDo App Pod
kubectl apply -f .infrastructure/todoapp-pod.yml
Test ToDo App with Port Forward
kubectl port-forward pod/todoapp 8000:8000 -n todoapp
# Open browser at http://localhost:8000
Test Using Busybox Curl
kubectl exec -it busybox -n todoapp -- curl http://todoapp:8000/api/readiness/
kubectl exec -it busybox -n todoapp -- curl http://todoapp:8000/api/liveness/
