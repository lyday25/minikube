minikube start
minikube status

kubectl
alias k=kubectl
k
k get nodes
k get pods
k create ns test
k get ns
k apply -f deployment.yaml -n test
k apply -f service.yaml -n test
k get pods -n test

k get events
k get svc -n test

# TO launch your service
minikube service nginx -n test

# TO ENTER THE POD

k exec -it nginx-deployment-77d8468669-7ddwm -n test -- sh


k describe pod nginx-deployment-5cf6cf4669-9xjlt

# IF you want to delete

k delete -f