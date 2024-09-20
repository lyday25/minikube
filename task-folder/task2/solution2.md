# Task 2
1. Create a pod in Kubernetes call the pod web1, image is ngnix
2. Check the status of this pod, if with error delete it and fix the issue.
3. Check the status, if running create a file of your specification in the tmp folder

# Solution

kubectl run web1 --image=ngnix

kubectl run web1 --image=ngnix

k describe pod web1

k delete pod web1

# fix the issue

kubectl run web1 --image=nginx

 k exec -it web1 -- sh
