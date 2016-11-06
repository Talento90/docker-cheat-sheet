#docker-cheat-sheet


docker images
-------------
An image is a filesystem and parameters to use at runtime. It is **stateless** and **never changes**.

**build docker image**
docker build --build-arg ARG_NAME=ARG_VALUE  dockerfilePath -t <company>/<project-name>:<tag> -t company/core-project:latest

**get all docker images**
docker images

**remove docker image**
docker rmi node

**delete all docker images**
docker rmi $(docker images -q)


docker containers
-----------------
A container is a running **instance** of an image. 


**run container (detached)**
docker run --name container-name -d <company>/<image-name>:<tag>

**stop container by id or name**
docker stop container-name

**get running containers**
docker ps

**get all containers**
docker ps -a

**delete all docker containers**
docker rm $(docker ps -a -q)

**enter in some container**
docker exec -it container-name sh

**tail container logs**
docker logs -f container-name


dockerfile resources
--------------------

**install git**
apk add --no-cache git
