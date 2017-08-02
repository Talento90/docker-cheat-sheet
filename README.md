# Docker Cheat Sheet

Repository that contains my notes related with Docker!


## Docker Daemon

The background service running on the host that manages building, running and distributing Docker containers.

## Docker Images

A Docker image is a **read-only** and **stateless** template with instructions for creating a Docker container.

There are 2 types of images:

* **Base images** are images that have no parent images, usually images with an OS like ubuntu, alpine or debian.

* **Child images** are images that build on base images and add additional functionality.


### commands:

* **build docker image**

   _docker build --build-arg ARG_NAME=ARG_VALUE  dockerfilePath -t company/project-name:tag_

* **list all docker images**

   _docker images_

* **remove docker image**

   _docker rmi node_
* **remove docker dangling images (with repository and tag as \<none\>)**
   
   _docker rmi $(docker images --quiet --filter "dangling=true")_
   
   _docker rmi $(docker images -q -f "dangling=true")_

* **delete all docker images**

   _docker rmi $(docker images -a -q)_

* **get image from a registry**

   _docker pull imageId_
   

## Docker Containers

A Docker container is a **runnable instance** of a Docker image. It includes an application and all of its dependencies. It shares the kernel with other containers, and runs as an isolated process in user space on the host OS.

### commands:

* **start container**

   _docker start container-name_

* **run container**

   _docker run --name container-name -d -e ENV_KEY="env value" -p 8888:80 company/image-name:tag_
   
   * **--name** allows you to specify a container name
   * **-d** will create a container with the process detached from our terminal
   * **-e** is how you pass environment variables to the container
   * **ENV_KEY** is the environment variabl that you want to pass
   * **-P** will publish all the exposed container ports to random ports on the Docker host
   * **-p** will expose port 80 inside the container and port 8888 on the host machine (**host machine:container**)

* **stop container by id or name**

   _docker stop container-name_

* **list running containers**

   _docker ps_

* **list all containers**

   _docker ps -a_

* **delete all docker containers**

   _docker rm $(docker ps -a -q)_

* **delete all docker containers and volumes**

   _docker rm -v $(docker ps -a -q)_


* **enter in some container**

   _docker exec -it container-name sh/bash_

* **tail container logs**

   _docker logs -f container-name_
   
* **container info**

   _docker inspect container-name_


## Docker Volumes

Volumes are designed to persist data, independent of the container’s life cycle.


### commands:

* * **list all volumes**

   _docker volume ps_
   
* **delete all volumes**

   _docker volume rm $(docker volume ls -q)_


## Docker Compose

Compose is a tool for defining and running multi-container Docker applications.

### commands:

* **build compose**

   _docker-compose build_

* **compose up**

   _docker-compose up_
