# CREATE NAMESPACE

k create ns application

k run web1 --image httpd:alpine3.20 --namespace application --dry-run=client -o yaml > pod.yaml

kubectl -n application get pod web1  -o yaml

kubectl -n application get pod web1  -o json


kubectl -n application get pod web1  -o jsonpath={.status}


kubectl -n application get pod web1  -o jsonpath={.status.phase}