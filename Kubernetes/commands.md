# Basics
Command | Description
------------ | -------------
`kubectl`  | control the containers across nodes
`minikube` | tool for running Kubernetes locally on one machine.

# Installation
Command | Description
------------ | -------------
`brew install Kubectl` | 
`brew link kubernetes-cli` |
`brew install minikube` | 
 

Check installation | .
------------ | -------------
`docker version` | 
`kubectl version` |
`minikube version` |
`sysctl -a | grep -E --color 'machdep.cpu.features|VMX'` | check that Mac OS is set up to run virtual machines
`virtualbox` | 

# Starting it up / status
Command | Description
------------ | -------------
`minikube start` | 
`minikube status` | 
`kubectl logs pod/finalcountdown-tcqlm` | Read logs (stdout and stderr) on the given pod
`kubectl create -f helloworld.yaml` | launch pods & containers defined in helloworld.yaml


# Inspecting
kubectl get all
kubectl get nodes
kubectl get deployment/helloworld -o yaml
kubectl get service
kubectl get service/helloworld
kubectl get service/helloworld -o yaml

kubectl describe po/helloworld-789bb655f-kcndz


# Expose a service
kubectl expose deployment helloworld --type=NodePort

minikube service helloworld

# Minicube web interface
minikube dashboard

# Tear down environment
kubectl delete pods --all

kubectl delete --name helloworld

kubectl delete --all
minikube delete

minikube delete

killall minikube
killall kubectl


# Labels
kubectl get pods --show-labels

## Setting
kubectl label po/helloworld app=helloworldapp --overwrite

## Deleting
kubectl label po/helloworld app-

## Filtering by labels
kubectl get pots --selector env=production
kubectl delete pods -l dev-lead=karthik

# Updating images
kubectl set image deployment/navbar-deployment helloworld=karthequiam/helloworld:blue
kubectl get all
kubectl set image deployment/navbar-deployment helloworld=karthequian/helloworld:blue
kubectl get all
kubectl get deployments

## Undo an image update
kubectl rollout history deployment/navbar-deployment
kubectl rollout undo deployment/navbar-deployment
kubectl rollout undo deployment/navbar-deployment --to-revision=1


# Log into a container
kubectl exec -it navbar-deployment-685664588f-wq5rl /bin/bash
kubectl exec -it navbar-deployment-685664588f-wq5rl -c helloworld /bin/bash

# Enable addons
minikube addons list
minikube addons enable dashboard
minikube addons enable metrics-server
minikube status

# Use secrets
kubectl create secret generic apikey --from-literal=api_key=123456789
kubectl get secrets
kubectl get secrets/apikey
kubectl get secrets/apikey -o yaml


# References
Most of the commands were used for this course:
https://www.linkedin.com/learning/learning-kubernetes/
