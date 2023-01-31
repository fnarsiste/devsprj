# Dockerise
docker build -t fnarsiste/devopswebapp:latest .

docker build -t fnarsiste/devopswebapp:1.0 .

# Dérmarrer et vérifier le status
minikube start
minikube status

# Appliquer les YMLs 
kubectl apply -f namespace.yml
kubens esgis-devops
kubectl apply -f phpdeploy.yml  
kubectl apply -f mydeploy.yml
kubectl apply -f mysql-secret.yml   

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