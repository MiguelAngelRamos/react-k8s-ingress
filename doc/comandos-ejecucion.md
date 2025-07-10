## 1. Habilita el Ingress Controller en Minikube

```sh
minikube addons enable ingress
```

## 2. Verificar que Ingress Controller esté corriendo

```sh
kubectl get pods -n ingress-nginx
```

## 3. comandos de Ejecucion

```sh
kubectl apply -f k8s/react-namespace.yaml
kubectl apply -f k8s/react-deployment.yaml
kubectl apply -f k8s/react-service.yaml
kubectl apply -f k8s/react-hpa.yaml
kubectl apply -f k8s/react-ingress.yaml
```
