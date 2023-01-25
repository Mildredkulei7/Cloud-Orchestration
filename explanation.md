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

The services created as below;

NAME          TYPE           CLUSTER-IP    EXTERNAL-IP      PORT(S)          AGE
backendsvc    LoadBalancer   10.84.0.61    34.125.166.108   8001:31461/TCP   15m
clientsvc     LoadBalancer   10.84.14.36   34.118.243.70    8000:30578/TCP   23m
kubernetes    ClusterIP      10.84.0.1     <none>           443/TCP          88m

We got 3 nodes created;

NAME                                          STATUS   ROLES    AGE   VERSION
gke-yolo-cluster-default-pool-973eb09d-0k2k   Ready    <none>   85m   v1.24.8-gke.2000
gke-yolo-cluster-default-pool-973eb09d-7vm6   Ready    <none>   85m   v1.24.8-gke.2000
gke-yolo-cluster-default-pool-973eb09d-n4tz   Ready    <none>   85m   v1.24.8-gke.2000

The 2 pods created:

NAME                           READY   STATUS             RESTARTS   AGE
web-56478f4876-5l4kg           0/1     ImagePullBackOff   0          73m
web-backend-6f96fc874c-zxb75   0/1     ErrImagePull       0          73m

Front_end service:   34.118.243.70 

Backend_service:  34.125.166.108


