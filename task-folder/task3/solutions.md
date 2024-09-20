# Task 3

1. Create a namespace called myspace and a pod with image ngnix and nginx1 on that namespace

2. Create a pod that was just described using yaml and edit container nginx1-container

3. Create a busybox pod that runs the command ”ls”, check the output.



k run nginx1 --image=ngnix -n myspace

k run nginx1 --image=nginx -n myspace --dry-run=client -o yaml > pod.yaml

# Do a vi and edit name of container
vi pod.yaml

# Apply

k apply -f pod.yaml

k run busybox --image=busybox --command --restart=Never -it -- ls