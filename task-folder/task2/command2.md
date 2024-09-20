kubectl run web1 --image=ngnix

kubectl run web1 --image=ngnix

k describe pod web1

k delete pod web1

# fix the issue

kubectl run web1 --image=nginx

 k exec -it web1 -- sh
