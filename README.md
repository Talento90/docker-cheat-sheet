#docker-cheat-sheet


docker images
-------------
An image is a filesystem and parameters to use at runtime. It is **stateless** and **never changes**.

**build docker image**

docker build --build-arg ARG_NAME=ARG_VALUE  dockerfilePath -t <company>/<project-name>:<tag> -t company/core-project:latest

* **get all docker images**

   _docker images_

* **remove docker image**

   _docker rmi node_

* **delete all docker images**

   _docker rmi $(docker images -q)_


docker containers
-----------------
A container is a running **instance** of an image. 


* **run container (detached)**

   _docker run --name container-name -d <company>/<image-name>:<tag>_

* **stop container by id or name**

   _docker stop container-name_

* **get running containers**

   _docker ps_

* **get all containers**

   _docker ps -a_

* **delete all docker containers**

   _docker rm $(docker ps -a -q)_

* **enter in some container**

   _docker exec -it container-name sh_

* **tail container logs**

   _docker logs -f container-name_


dockerfile resources
--------------------

* **install git**

   _apk add --no-cache git_
