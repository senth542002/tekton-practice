#Tekton

Tekton is a powerful and flexible open-source framework for creating CI/CD systems, allowing developers to build, test, and deploy across cloud providers and on-premise systems.

https://tekton.dev/docs/getting-started/

1) Create kubernetes cluster -> minikube start

2) Installation
To install the core component of Tekton, Tekton Pipelines, run the command below:

kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

3) Check progress -> kubectl get pods --namespace tekton-pipelines


#Tekton Dashboard -> https://katacoda.com/tektoncd/scenarios/dashboard

#To install the Tekton Dashboard prerequisites, run the following command: 

kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/previous/v0.20.0/release.yaml

kubectl get pods -n tekton-pipelines

#To install the Tekton Dashboard, run the following command: 

kubectl apply --filename https://storage.googleapis.com/tekton-releases/dashboard/previous/v0.13.0/tekton-dashboard-release.yaml

kubectl get pods -n tekton-pipelines

#View Tekton dashboard service
kubectl get svc tekton-dashboard -n tekton-pipelines

#The Tekton Dashboard Service is exposed on port 9097. So, set up a port forward for the tekton-dashboard Service on port 9097:

kubectl port-forward -n tekton-pipelines --address=0.0.0.0 service/tekton-dashboard 80:9097 > /dev/null 2>&1 &

