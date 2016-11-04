# docker-cheat-sheet


#Build docker image
docker build --build-arg HTTP_PROXY=ARG_VALUE  . -t nos/cti3-es-indexer:1.0.0 -t nos/cti3-es-indexer:latest

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



...DockerFile...

FROM mhart/alpine-node:6.9.1

MAINTAINER NOS Inovação SA

ARG GIT_COMMIT=0

ENV GIT_COMMIT $GIT_COMMIT

ADD . /cti3-es-indexer/

WORKDIR cti3-es-indexer

RUN npm install
RUN GIT_COMMIT=$GIT_COMMIT npm run build
RUN npm prune

CMD ["npm", "start"]
