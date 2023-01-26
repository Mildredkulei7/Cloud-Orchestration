
There is a detailed eplanation on container ochestration using GKE on explanation.md file.

Site Link:

Front_end service: http://34.118.243.70:8000/

Backend_service:  http://34.125.166.108:8001/


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
## Requirements
Make sure that you have the following installed:
- [node](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04) 
- npm 
- [MongoDB](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) and start the mongodb service with `sudo service mongod start`

### Navigate to the Client Folder 
 `cd client`

### Run the folllowing command to install the dependencies 
 `npm install`

### Run the folllowing to start the app
 `npm start`

### Open a new terminal and run the same commands in the backend folder
 `cd ../backend`

 `npm install`

 `npm start`

 ### Go ahead a nd add a product (note that the price field only takes a numeric input)
 
## Creating the Docker Containarisation to replicate the E-commerce above

 ### Install the following
* node
* npm
* mongoDB

### npm
1. Navigate to client folder
Run:
cd client
npm install
npm start

2. Navigate to client folder
Run:
cd client
npm install
npm start

### mongoDB
Sighn-up for mongodb online service
create a cluster

### Steps
1. create .env file
2. create Dockerfile in each container; client & backend containers
3. create docker-compose yaml file
4. build the docker compose image
 using "Docker compose build"
5. Start the Application
 using "Docker compose up"
6. Docker networking
Confirm that both containers plus the mongodb are on the same network
7. created account on dockerhub
pushed the images there; https://hub.docker.com/repository/docker/mildredkulei/yolomy-app

link to dockerhub images

frontend image: https://hub.docker.com/layers/mildredkulei/yolomy-app/yoloweb

backend image: https://hub.docker.com/layers/mildredkulei/yolomy-app/yoloapi 

