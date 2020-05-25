
# Use Service Type LoadBalancer for exposing apps to external traffic on Rancher


### Pre-requisites 

* Rancher app
* Kubernetes cluster linked to Rancher app


Node | IP Address
---- | ----------
Rancher app | 10.102.216.12
Kubernetes Master Node | 10.102.216.13
Kubernetes Worker Node 1 | 10.102.216.14
Kubernetes Worker Node 2 | 10.102.216.15


### Deploy App 

Screenshot of cluster health

kubectl create namespace guestbook-app 

Screenshot of guestbook.yaml upload

kubectl apply -f guestbook.yaml -n guestbook-app

Wait for a min to see all pods become green
Screenshot of all green apps

kubectl apply -f nodeport.yaml -n guestbook-app
Screenshot of nodeport yaml upload


used guestbook app from this example - https://kubernetes.io/docs/tutorials/stateless-application/guestbook/
till NodePort

Screenshot of NodePort service & command line showing port number

Add a few commands to show if data is being stored in RedisDB or not
Screenshot of all NodePorts working on 3 nodes



kubectl delete -f nodeport.yaml -n guestbook-app
Screenshot of deleting nodeport



kubectl apply -f rbac.yaml (in default ns)
Screenshot of rbac yaml upload 

kubectl apply -f vip.yaml (in default ns)
Screenshot of rbac yaml upload 

kubectl apply -f ipam.yaml (in System project!! )
Screenshot of ipam yaml upload 

kubectl apply -f cic-vpx.yaml -n guestbook-app
Screenshot of cic
Takes about a min



kubectl apply -f loadbalancer.yaml -n guestbook-app









