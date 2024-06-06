# Inception (Docker research)

## Project description
The aim of this project is to compose a collection of different Docker containers in order to host a WordPress website. The following containers are being used: 
- NGINX (in order to host server)
- MariaDB (Database)
- WordPress (Frontend)

### Resources


### Useful commands

**Running a docker container**
docker-compose up -d
The -d flag runs the containers in the background (detached mode)

*Verify if service is running*
docker ps

*Stopping all containers*
docker-compose down
docker-compose stop
*Stopping a specific service*
docker-compose stop db


### To dos

- [] Run NGINX container
- [] Run WordPress container
- [] Run MariaDB container
