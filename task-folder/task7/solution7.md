# Task 7 - Persistent volume

In namespace mct create a persistence volume  mct-pv. It should have capacity 100Mi with access mode ReadWriteOnce and hostpath /tmp/data, no storage class named defined.

In the same namespace create  a PersistentVolumeClaim  called mct-pvc, it should request 100MI and access mode ReadWriteOnce.


N/B the PVC should be bound to the PV correctly.


In the same namespace create a pod called nginx-mct using the image nginx while the container name is mct-container, which mounts the volume at /tmp/projectdata

# Solution

minikube start
alias k=kubectl
k create ns mct
k apply -f mct

k apply -f mct-pvc.yaml

k get pvc -n mct
k apply -f nginx-pod.yaml

# To get more information
k get pod -n mct -o wide

k describe pod nginx-mct -n mct
k delete ns mct
