# This is a Fulllstack Microservice architecture Project , Using React for frontend Nodejs for backend and Mongo db for storage 

# .......................................................................................#


  ## 1. CHOICE OF IMAGE

   # Frontend (React) kencehz/yoloclient:v1.0.0

    ** Node-14  - Containes all build command needed
    ** Alpine - alpine:3.16.7 - This provides the base image linux which is lightweiht in naturre

   ## Backend (Nodejs)  kencehz/yolobackend:v1.0.0

    ** Node-14  - Containes all build command needed
    ** Alpine - alpine:3.16.7 - This provides the base image linux which is lightweiht in nature

  ## 2. Docker Directive for setting up the docker images

     ** Some of commands have used to create this file are :

     -WORKDIR -Setting up working directorate
     -COPY package*.json ./ - Copy the package.json and package-lock.json files to the container
     -RUN npm install -  Install application dependecies
     -FROM
     -CMD

 ## 3. Docker Compose Networking & Volumes

  -All the three containers run on a common network which is
      app-net  ,,,,, and runs on bridge driver as defined in the docker-compose.yaml file
    
                networks:
                app-net:
                name: app-net
                driver: bridge
                attachable: true
                ipam:
                config:
                    - subnet: 172.20.0.0/16 
                    ip_range: 172.20.0.0/16 


     -Frontend: 3000:3000 , Backend: 5000:5000 ,MongoDB: 27017:27017 ,, this are ports which act as the point of communication


 ## 4.  Git workflow

   -I made use of git for my project flow:
     some of commands used include : 

      git clone git@github.com:Vinge1718/yolo.git
    - This comes with the project already initialised 
       # git add .
       # git commit -m "Commitmessage"
       # git push

## 5. RUnning of Applicatiion of Good practises

  -To Run the project have made use of  docker build command :
       **sudo docker compose up --build**
   -Some of best practices used include :
        **Using Alpine as the base image this makes the images to be small in size since alpine is lightweight**
        **Semantic versioning versioning which gives unique identity for each version realised hence fallingbacak can be easy incase of a system breakdown**


    


![Alt text](dockerhubimage.png)


     
