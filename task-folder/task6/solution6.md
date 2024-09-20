# Task 6

(How do we persist data in k8s)

                       IF  PODS ARE EPHEMERAL


1. Deploy a pod called nginx1-pod with the image nginx

2. Inside the pod create a file text1.txt  inside one of the directories(tmp) saying 

“i love devops” and inside file text.txt echo  today's date

3. Kill this pod nginx-pod

4. Create the pod back and check if the files are still there inside that directory



# Solution

k run nginx1 --image=nginx

k get pod

k exec -it nginx1 -- sh

k delete pod nginx1


# Solution to retain data in a pod 
vi volume.yaml

# paste this
apiVersion: v1

kind: Pod

metadata:

  name: pod-with-no-volume

spec:



  containers:

  - image: centos

    name: centos-container

    command: ["/bin/bash", "-c", "while true; do echo 'date'; sleep 30; done >> /var/log/output.log"]


    volumeMounts:

    - name: log-dir

      mountPath: /var/log

  volumes:

  - name: log-dir

    hostPath:

      # Ensure the file directory is created.

      path: /var/log

      type: Directory

      # Apply
      k apply -f volume.yaml
      k get pod

      # Enter the pod
      k exec pod-with-no-volume  -it -- sh

      k delete -f volume.yaml
      
      # BUT THE ABOVE SOLUTION WILL NOT WORK IN PROPER COMPANY SETTINGS BC THE DEVELOPERS MAY NOT BE AWARE OF THE FILESE SYSTEM IN THE KUBERNETES CLUSTERS SO WHAT IS USED IS CALL PERSISTENT VOLUME AND PERSISTENT VOLUME CLAIMS