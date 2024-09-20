# Task 4
1. Create a pod called busybox with image busybox, make sure the pod does not run. The end result must be in a yaml file called echo.yaml. Please change the name of the container to busybox-container
2. Apply and create the pod using the yaml file created
3. Check the status of the pod and if running pls exec into the pod and write to a file "I love cloud computing"

# Solution
# Create the pod and image
kubectl run busybox --image=busybox

# Pod must not run, end result in a yaml file
k run busybox --image=busybox --dry-run=client -o yaml > echo.yaml

# Change container name to busybox-container, Do a vi and edit name of container
vi echo.yaml

# Apply using yaml file
k apply -f echo.yaml

# An error occured after this. To fix the issue, delete the pod
k delete pod busybox

# Rename the pod and the yaml file. This is necessary because pod and image have same name and echo.yaml already exist from the initial creation of pod busybox. Then do the dry run again.
k run busybox1 --image=busybox --dry-run=client -o yaml > echo1.yaml

k apply -f echo1.yaml

# Check status of pod


