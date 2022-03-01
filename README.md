# Kubernetes pratice

### Installing

kubernetes

> choco install kubernetes-cli


Minikube

> choco install minikube


### Main commands

```
kubectl create -f pod.yml
kubectl apply -f pod.yml
kubectl get pods

kubectl delete pod nginx-2

kubectl replace -f pod.yml

kubectl scale --replicas=6 -f pod.yml

kubectl scale --replicas=8 replicaset aplicacao-rs

kubectl get replicaset
kubectl get replicationcontroller

kubectl describe replicaset frontend-rs
kubectl describe deployment frontend-db

kubectl get replicaset
kubectl get all

kubectl delete deployment frontend-dp
kubectl create -f dp.yaml --save-config --record
kubectl rollout status deployments/frontend-dp

kubectl rollout history deployments/frontend-dp

kubectl set image deployment frontend-dp frontend-container=nginx:1.18 --record

kubectl rollout undo deployment/frontend-dp

kubectl rollout undo deployment/frontend-dp --to-revision=1

kubectl exec -it webapp-asamkd23j34-3j4m bash
apt-get update
apt search mysql-client
apt install default-mysql-client -y
mysql -h 172.17.0.3 -uroot -ppassword geek

cat /etc/resolv.conf

## service

minikube delete
minikube start
kubectl create -f deployments/frontend-dp.yaml --save-config --record

kubectl create -f services/frontend-svc.yaml --save-config --record

kubectl get all

minikube ip

minikube service frontend-svc --url
```

### deploy

```
kubectl create -f microservicos/namespaces/ --save-config --record
kubectl create -f microservicos/deployments/ --save-config --record
kubectl create -f microservicos/services/ --save-config --record

kubectl get all -n vote

minikube service --url -n vote
```