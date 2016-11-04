# docker-cheat-sheet

#remove docker image
docker rmi node

#delete all docker containers
docker rm $(docker ps -a -q)

#delete all docker images
docker rmi $(docker images -q)

#Build docker image
docker build --build-arg HTTP_PROXY=ARG_VALUE  . -t nos/cti3-es-indexer:1.0.0 -t nos/cti3-es-indexer:latest
params:<repo-user>/project:tag

#Get all docker images
docker images

#Get all containers
docker ps -a

#Stop container by id or name
docker stop container_name

#Enter in some container
docker exec -it cti3-es-indexer sh

#Tail container logs
docker logs -f cti3-es-indexer

#Run docker container (detached)
docker run --name cti3-es-indexer -d nos/cti3-es-indexer



GET GIT
apk add --no-cache git


#Passing arguments and Enviroment variables
ARG KAFKA_VERSION=0.10.1.0
ARG SCALA_VERSION=2.11

RUN apk add --update unzip wget curl docker jq coreutils

ENV KAFKA_VERSION $KAFKA_VERSION
ENV SCALA_VERSION $SCALA_VERSION
