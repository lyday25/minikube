kubectl
alias k=kubectl
k
k get nodes
k get pods
k get ns
k apply -f deployment.yaml -n test
k apply -f service.yaml -n test
k get pods -n test

k get events

k describe pod nginx-deployment-5cf6cf4669-9xjlt