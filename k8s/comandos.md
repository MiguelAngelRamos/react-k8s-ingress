Desde la terminal ejecuta estos comandos (Nota: Deberias estar en la carpeta de los YAML)

```sh
kubectl apply -f react-deployment.yaml
```

```sh
kubectl apply -f react-service.yaml
```

## Ejemplo del resultado esperado
```sh

S C:\Users\Miguel\Desktop\Curso-Kubernetes\react-k8\k8s> kubectl apply -f react-service.yaml
service/react-app created
service/react-app created
PS C:\Users\Miguel\Desktop\Curso-Kubernetes\react-k8\k8s> minikube service react-app
|-----------|-----------|-------------|---------------------------|
| NAMESPACE |   NAME    | TARGET PORT |            URL            |
|-----------|-----------|-------------|---------------------------|
| default   | react-app |          80 | http://192.168.49.2:30000 |
|-----------|-----------|-------------|---------------------------|
🏃  Starting tunnel for service react-app.
|-----------|-----------|-------------|------------------------|
| NAMESPACE |   NAME    | TARGET PORT |          URL           |
|-----------|-----------|-------------|------------------------|
| default   | react-app |             | http://127.0.0.1:56414 |
|-----------|-----------|-------------|------------------------|
🎉  Opening service default/react-app in default browser...
❗  Because you are using a Docker driver on windows, the terminal needs to be open to run it.
```