Docker commands list:
====================

Containers:
-----------

Note: In place of mycontainer we can use container Id also

Create and start a new container based on an image.

        docker run --name mycontainer myimage:tag

Restart a container.

        docker restart mycontainer

Pause a running container.

        docker pause mycontainer

Unpause a paused container.

        docker unpause mycontainer

List running containers.

        docker ps

List all containers, including stopped ones.

        docker ps -a

Get the full details of the container

        docker inspect mycontainer

Login to the container

        docker exec -t mycontainer /bin/bash 

Start the stopped container

        docker start mycontainer

Stop the running container

        docker stop mycontainer

Stop all the containers at a time.

        docker stop $(docker ps -aq)

Remove one or more containers.

        docker rm mycontainer

Remove all containers at a time.

        docker rm $(docker ps -aq)

View the logs of a container.

        docker logs mycontainer

Images:
--------

Upload an image to the registry.

                docker push myimage:tag


Download an image from a registry.

                docker pull myimage:tag


Build a Docker image from a Dockerfile.

                docker build -t myimage:tag .

List locally available images.

                docker images

Search the image

                docker search myimage

Remove one or more images.

                docker rmi myimage:tag

Remove all the  images at a time.

                docker rmi $(docker images -aq)

List Dangling Images.(Dangling images in Docker refer to images that are not associated with any containers or tags. )

                docker image -f "dangling=true"

Remove Dangling Images.

                docker image prune

Volume:
-------

List all Docker volumes on the host.

        docker volume ls

Create a new Docker volume.

        docker volume create myvolume

Attach a volume to a container when running it. This creates a new volume if it doesn't already exist.

        docker run -v myvolume:/path/in/container myimage

Attach a volume to a container using the --mount flag. This provides more advanced options for volume configuration.

        docker run --mount source=myvolume,target=/path/in/container myimage

Display detailed information about a specific volume.

        docker volume inspect myvolume

Remove one or more Docker volumes.

        docker volume rm myvolume

Remove all unused Docker volumes.

        docker volume prune

Networking:
-----------

List all the networks created on the Docker host.

        docker network ls

Create a new custom bridge, overlay, or host network.

        docker network create <mynetwork>

Display detailed information about a specific network.

        docker network inspect <mynetwork>

Remove one or more networks.

        docker network rm <mynetwork>

Remove all unused networks.

        docker network prune

Attach a container to a network.

        docker network connect <mynetwork> <mycontainer>

Detach a container from a network

        docker network disconnect <mynetwork> <mycontainer>

Docker-compose:
---------------

Start containers defined in the docker-compose.yml file. It creates and starts containers for all services defined in the Compose file.

        docker-compose up

Start containers in detached mode, running them in the background.

        docker-compose up -d

Stop and remove containers, networks, and volumes defined in the docker-compose.yml file.

        docker-compose down

Build or rebuild Docker images defined in the Compose file.

        docker-compose build

List the status of containers defined in the Compose file.

        docker-compose ps

View logs from containers defined in the Compose file. You can specify a service name to view logs for a specific service.

        docker-compose logs

        docker-compose logs myservice

Pull the latest images for services defined in the Compose file without starting containers.

        docker-compose pull

Restart containers defined in the Compose file.

        docker-compose restart

Pause and unpause services.

        docker-compose pause myservice
        
        docker-compose unpause myservice

Scale the number of containers for a service. For example, to run three instances of a service.

        docker-compose up -d
        
        docker-compose scale myservice=3






