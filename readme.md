# Dockerise
docker build -t fnarsiste/devopswebapp:latest .

docker build -t fnarsiste/devopswebapp:1.0 .

# Dérmarrer et vérifier le status
minikube start
minikube status

# Appliquer les YMLs 
kubectl apply -f namespace.yaml
kubectl apply -f php-deployment.yaml  
kubectl apply -f mysql-deployment.yaml

# Définir le namespace de travail
kubens test 

# Lister les pods
kubectl get pods
kubectl describe pod pod-id

# Lister les services
kubectl get svc

# Obtenir infos
kubectl cluster-info
minikube service [name] --url=true

# Open a bash
kubectl exec -it [pod-id] bash