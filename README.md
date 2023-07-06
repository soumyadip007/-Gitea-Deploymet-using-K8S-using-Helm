# Gitea Deployment using K8S using Helm

This repository contains the necessary files and instructions to deploy Gitea, a self-hosted Git service, on Kubernetes using Helm.

## Deployment

To deploy Gitea, follow these steps:

1. Apply the deployment manifest:
kubectl apply -f ./valina-k8s/deployment.yaml

2. Apply the service manifest:
kubectl apply -f ./valina-k8s/service.yaml

3. Verify the deployment and service:
kubectl get deployments -n gitea-ns
kubectl get services -n gitea-ns
kubectl get deployments -n gitea-ns


## Clean Up

To delete the Gitea deployment, run the following command:
kubectl delete deployment gitea-deployment


## Running Gitea Locally (Optional)

If you want to run Gitea locally without Kubernetes, you can use the following command:
docker run -p 3000:3000 gitea/gitea

## Helm Charts (Optional)

This repository also includes Helm charts for deploying Gitea. To use Helm, follow these steps:

1. Install the Helm chart:
helm install helm ./helm

2. List the installed Helm releases:
helm list

3. Uninstall the Helm release:
helm uninstall helm

4. To view the rendered Helm chart without installing, use the following command:
helm template helm ./helm --debug

5. Release : helm package ./gitea 

6. Indexing : helm repo index ./gitea


## Important Note (minikube)

If you are using minikube, make sure to run the following command before deploying Gitea:
minikube tunnel


This command sets up a network tunnel that allows the Kubernetes services to be reachable from the host machine.

Please note that the above README assumes that you have the necessary files in the specified directories (./valina-k8s/deployment.yaml, ./valina-k8s/service.yaml, ./helm).

Make sure to replace any placeholders or fill in any missing details according to your specific use case before using the README.