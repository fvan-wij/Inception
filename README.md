# Inception (Docker research)

## Project description
The aim of this project is to compose a collection of different Docker containers in order to host a WordPress website. The following containers are being used: 
- NGINX (in order to host server)
- MariaDB (Database)
- WordPress (Frontend)

### How Docker & Docker Compose works

Docker allows you to package apps and their dependancies in so called containers, which are lightweight, consistent across different platforms and isolated from the host system.

Docker Compose allows you to manage and run multiple Docker containers in a network so that they can communicate with eachother. 

Compared with a VM, Docker offers some advantages such as the fact that it uses less resources from the host and only uses the bare minimum resources to run the desired applications and dependancies. The fact that containers are isolated packages, makes them very portable.

### Resources

### Images

An image is a read-only template with instructions for creating a Docker container. It might contain steps necessary to run images based on the Ubuntu image, but also installs the Apache web serer to run your desired application.

These images can be grabbed from Docker Hub or you can create your own images using a Dockerfile. Each instruction in a Docker file creates a layer in the image. When you change the Dockerfile and rebuild, only the influenced layer will be rebuilt, which makes it lightweight.

### Containers

A container is a runnable instance of an image. You can create, start, stop, move or delete a container using the Docker API.
By default, a container is relatively isolated, but can be configured in a way so that it behaves in a synergetic way with other containers.


### Docker engine

The Docker engine is the core component of Docker. It bundles your application and its dependencies into a single package, called a container. It also includes the Docker Deamon, which is a background process that manages containers. 

It works like this:

1. You create a Dockerfile, which includes all the necessary steps to run a piece of software;

2. You use Docker by running 'docker build' and specifying the path to the Dockerfile. The Docker daemon reads the instructions in theDockerfile and builds the image.

3. Once the image is built, you can use Docker to run the image as a container using the 'docker run' command, it then proceeds to run the app in the container.

4. Docker manages resources such as CPU, memory, and storage for the container

5. Docker can be used to view, stop, and manage the containers on your system. It can also be pushed to a registry, such as Docker Hub so that it can be shared with others

### To find out:

- Why is network: hosts or links: not allowed in your docker-compose file?
- Why is --link not allowed in the Makefile?
- Why is tail -f not allowed?
- What would be wrong with infinite loops such as sleep infinity, tail -f /dev/null, tail -f /dev/random
- The pertinence of the directory structure required for this project


### Dockerfiles vs Docker-compose files

A Dockerfile is used to build a single Docker image, while Docker-compose is used to define and run multiple containers as a single app.
The syntax is also different. 

### Useful commands

docker build: Used to build a Docker image from a Dockerfile.
docker run: Used to run a Docker container based on a Docker image.
docker pull: Used to pull a Docker image from a registry, such as Docker Hub.
docker push: Used to push a Docker image to a registry.
docker ps: Used to list the running Docker containers on a system.
docker stop: Used to stop a running Docker container.
docker rm: Used to remove a Docker container.
docker rmi: Used to remove a Docker image.
docker exec: Used to execute a command in a running Docker container.
docker logs: Used to view the logs for a Docker container.

**Running a docker container**
docker-compose up -d
The -d flag runs the containers in the background (detached mode)

**Verify if service is running**
docker ps

**Stopping all containers**
docker-compose down
docker-compose stop

**Stopping a specific service**
docker-compose stop db


### To dos

- [] Run NGINX container
- [] Run WordPress container
- [] Run MariaDB container
