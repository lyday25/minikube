minikube start
minikube status

alias k=kubectl
k
k get nodes
k get pods
k apply -f deployment.yaml
k apply -f service.yaml 
k get pods

k get events
k get svc 

# TO launch your service
minikube service jenkins 

# TO ENTER THE POD

k exec -it jenkins-f56c6888f-z9vpj -- sh


# IF you want to delete

k delete -f

# for troubleshooting

k get logs (put pod name)

