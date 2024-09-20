# Task 1

1. Create a single pod of image httpd:alpine3.20 in namespace application (check if namespace exist or not)

2. Pls the pod should be name web1 and the container should be name web-container

3. Write  a shell script to output the status of the pod

# Solution

# CREATE NAMESPACE

k create ns application

k run web1 --image httpd:alpine3.20 --namespace application --dry-run=client -o yaml > pod.yaml

kubectl -n application get pod web1  -o yaml

kubectl -n application get pod web1  -o json


kubectl -n application get pod web1  -o jsonpath={.status}


kubectl -n application get pod web1  -o jsonpath={.status.phase}