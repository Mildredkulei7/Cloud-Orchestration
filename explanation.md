. Dockerfile directives used in the creation and running of each container.
Built the containers using the respective client & backend folders, specified
same network on both containers and placed them on different ports.

2. Docker-compose Networking (Application port allocation and a bridge network implementation) where necessary.
I placed both containers on same network but on different ports so that they can shared data.

3. Successful running of the applications and if not, debugging measures applied.
The Application compiled Successfuly.

4. Good practices such as Docker image tag naming standards for ease of identification of images and containers. 
named the images according to their services plus the application name(yolo);
e.g 
* yoloapi - for backend servises
* yoloweb - for client services
* mongo - for mongodb

5. Docker-compose volume definition and usage (where necessary).

-----------------------------------------------------------------
# PROJECT NAME
Ochestration of yolo app using google kubernetes Engine

# Steps
~ login to your google cloud shell, use your google account and create a project to work on.
~ select your prefered region and zone
~ Go to the root of your project and create the following files, all under one folder namely "manifests"
    ~client.yml
    ~backend.yml
    ~mongodb.yml
~ to create aech service , run the following command
    ~kubectl apply -f client.yaml
    ~kubectl apply -f backend.yaml
    ~kubectl apply -f mongodb.yaml

~ confirm the service by running the below command
    ~kubectl get deployment 
    ~kubectl get statefulset

~ run the following to expose the ip address externally
Front-end service:

     kubectl expose deploy web --type=LoadBalancer --port=8000 --target-port=8000 --name=clientsvc

Backend:
    kubectl expose deploy web --type=LoadBalancer --port=8001 --target-port=8001 --name=clientsvc