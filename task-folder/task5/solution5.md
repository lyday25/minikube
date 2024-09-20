# Task 5
1. Create a Resource Quota called “reqQuota '' with hard limits of 1 CPU,1G memory and :":pods without creating it.
2. Get pods on all namespaces


# try to use help


k create resourcequota --help

# Command to create
K create quota reqQuota

# Command if you are not creating
kubectl create quota reqQuota --hard=cpu=1,memory=1G,pods=2 --dry-run=client --validate -o yaml > 5.yaml

# Now to get all the pods in all the namespaces
k get ns -A 

# get all pods in all namespaces

k get pods -A
