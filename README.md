# minikube
Kubernetes and minikube project
## Task for creating a docker container 
1. You are asked to create a container called web1-container with an image of nginx
2. Once the container has been created, run a command to confirm if the container has been created.
3. Now go inside the container and run the command ls
4. Look for a folder called tmp, cd to it and echo "I love cloud computing" into a text file called output.txt
-------------------------------------------------------------------------------------------------
## Solution
docker run -d nginx web1-container
docker container ls
docker exec -it 8dc3cc264784 sh
ls
cd tmp
echo "I love cloud computing" > output.txt
cat output.txt
exit




