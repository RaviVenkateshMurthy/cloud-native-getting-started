
# Use Service Type LoadBalancer for exposing apps to external traffic on Rancher


### Pre-requisites 

* Rancher app
* Kubernetes cluster linked to Rancher app


Node | IP Address
---- | ----------
Rancher app | 10.102.216.12
Kubernetes Master Node | 10.102.216.13
Kubernetes Worker Node | 10.102.216.14


### Deploy App 

kubectl create namespace guestbook-app 

kubectl apply -f guestbook.yaml -n guestbook-app
kubectl apply -f nodeport.yaml -n guestbook-app


used guestbook app from this example - https://kubernetes.io/docs/tutorials/stateless-application/guestbook/
till NodePort

Add a few commands to show if data is being stored in RedisDB or not

kubectl delete -f nodeport.yaml -n guestbook-app



kubectl apply -f rbac.yaml (in default ns)
kubectl apply -f vip.yaml (in default ns)
kubectl apply -f ipam.yaml (in System project!! )

kubectl apply -f cic-vpx.yaml -n guestbook-app



kubectl apply -f loadbalancer.yaml -n guestbook-app








