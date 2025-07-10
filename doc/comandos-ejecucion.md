## 1. Habilita el Ingress Controller en Minikube

```sh
minikube addons enable ingress
```

## 2. Verificar que Ingress Controller esté corriendo

```sh
kubectl get pods -n ingress-nginx
```

## 3. Ejecutar el Tunnel

```sh
minikube tunnel
```
## 4. comandos de Ejecucion

```sh
kubectl apply -f k8s/react-namespace.yaml
kubectl apply -f k8s/react-deployment.yaml
kubectl apply -f k8s/react-service.yaml
kubectl apply -f k8s/react-hpa.yaml
kubectl apply -f k8s/react-ingress.yaml
```

## 5. Configurar el Host de windows 

```sh
C:\Windows\System32\drivers\etc
```

En el archivo host abra un bloc de notas como Administrador e incluya la siguiente linea (al final):

```sh
127.0.0.1 react.local
```

## 6. En navegador

```sh
react.local
```

Deberias ver la app de react corriendo