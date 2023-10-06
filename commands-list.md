Containers list:
------------------

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














