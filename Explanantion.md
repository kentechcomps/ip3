# overview
-This is a e.commerce fullstack application with both frontend and backend using npm

# Commands used
Vagrant init - Create a vagrantfile
vagrant up & vagrant provision - This creates and launches my vm

# Playbook
I have defined 6 roles inside my playbook :

   1. docker-installation
Installs Docker Engine on the target virtual machine.

Tasks:

Installs required system dependencies

Adds Docker GPG key and repository

Installs docker-ce, docker-ce-cli, and containerd.io

Enables and starts the Docker service

2. docker-compose-installation
Installs Docker Compose, which is used to manage multi-container applications.

Tasks:

Downloads the latest Docker Compose binary

Adds executable permissions

Symlinks it to /usr/local/bin/docker-compose for global access

3. setup-nodejs
Installs Node.js, required for the backend service if the container builds locally (optional in your current Docker-based setup).

Tasks:

Adds NodeSource repository

Installs a specific Node.js version

4. setup-npm
Installs npm (Node Package Manager), generally comes with Node.js but can be installed/updated separately.

Tasks:

Ensures npm is installed and up to date

5. setup-mongodb
Prepares MongoDB support (either installing it locally or managing its Docker-based deployment).

Note: If MongoDB is run inside a container (as per your docker-compose.yml), this role might:

Create volumes

Ensure Docker network connectivity

Or be used for local MongoDB testing/development

6. backend-deployment
Deploys the Node.js backend API using Docker.

Tasks:

Pulls the image kencehz/yolobackend:v1.0.0 from Docker Hub

Creates a container on the custom Docker network (app-net)

Maps container port 5000 to host

Starts the backend using npm start or CMD from image

7. frontend-deployment
Deploys the React or frontend app using Docker.

Tasks:

Pulls the image kencehz/yoloclient:v1.0.0 from Docker Hub

Creates a container on the app-net network

Maps port 3000 to host

Depends on backend service to be running


# Commands that will be run

  -vagrant up
  -vagrant provision
  -vagrant ssh
  -docker ps