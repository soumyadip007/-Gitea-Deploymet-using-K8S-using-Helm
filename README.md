# Gitea-Deploymet-using-K8S-using-Helm
Gitea Deploymet usingn K8S using He

kubectl apply -f ./valina-k8s/deployment.yaml
kubectl apply -f ./valina-k8s/service.yaml

# imp 
minikube tunnel 


kubectl delete deployment gitea-deployment 

docker run -p 3000:3000 gitea/gitea 