#docker-cheat-sheet


docker images
-------------
A Docker image is a **read-only** and **stateless** template with instructions for creating a Docker container.

* **build docker image**

   _docker build --build-arg ARG_NAME=ARG_VALUE  dockerfilePath -t company/project-name:tag_

* **get all docker images**

   _docker images_

* **remove docker image**

   _docker rmi node_

* **delete all docker images**

   _docker rmi $(docker images -q)_


docker containers
-----------------
A Docker container is a **runnable instance** of a Docker image.


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

* **enter in some container**

   _docker exec -it container-name sh_

* **tail container logs**

   _docker logs -f container-name_


dockerfile resources
--------------------

* **install git**

   _apk add --no-cache git_
