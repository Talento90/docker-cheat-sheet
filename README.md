# docker-cheat-sheet

Repository that contains my notes related with Docker!


docker daemon
-------------
The background service running on the host that manages building, running and distributing Docker containers.

docker images
-------------
A Docker image is a **read-only** and **stateless** template with instructions for creating a Docker container.

* **build docker image**

   _docker build --build-arg ARG_NAME=ARG_VALUE  dockerfilePath -t company/project-name:tag_

* **get all docker images**

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

docker containers
-----------------
A Docker container is a **runnable instance** of a Docker image. It includes an application and all of its dependencies. It shares the kernel with other containers, and runs as an isolated process in user space on the host OS.

* **start container (detached)**

   _docker start container-name_

* **run container (detached)**

   _docker run --name container-name -d company/image-name:tag_

* **stop container by id or name**

   _docker stop container-name_

* **get running containers**

   _docker ps_

* **get all containers**

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

docker volumes
-----------------
Volumes are designed to persist data, independent of the container’s life cycle.

* **get all volumes**

   _docker volume ps_
   
* **delete all volumes**

   _docker volume rm $(docker volume ls -q)_

docker compose
--------------------
* **build compose**

   _docker-compose build_

* **compose up**

   _docker-compose up_
