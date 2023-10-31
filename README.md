# Kubernetes Demo

Diese beispiel demonstriert wie ein Container mit Kubernetes zum Laufen gebracht wird.

## Voraussetzungen

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) oder aehnliche runtime ist installiert
- [kubectl](https://kubernetes.io/docs/tasks/tools/) ist installiert
- [minikube](https://kubernetes.io/de/docs/tasks/tools/install-minikube/) ist installiert

## Ausfuehren

```bash
# Starten von Minikube Kubernetes Umgebung
minikube start

# Nutzen der Minikube Docker instanz am lokalen Rechner
eval $(minikube docker-env)

# Bau des Dockerfiles und erzeugen des Container Images
docker build -t myimage docker-demo/

# Container auf Minukube anstarten
kubectl apply -f deployment.yaml

# Ansehen der laufenden Pods
kubectl get pods

# Aufrufen des Webservers im lokalen browser
minikube service -n default myimage

# Loeschen des deployments
kubectl delete -f deployment.yaml
```
