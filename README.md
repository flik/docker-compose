# docker-compose
docker-compose examples

check basics
http://rapidsol.blogspot.com/2018/06/what-is-docker-and-docker-compose-and.html 


# Build Development Environment

For development purposes Docker environment has been created.

Docker is mandatory to run the application, you can install it by following this guide:

https://docs.docker.com/install/

Another needed tool is docker-compose(https://docs.docker.com/compose/install/)


After install and verify let's make little file which will help to understand docker usage.

The following example brings up a cluster comprising two Elasticsearch nodes. To bring up the cluster, use the docker-compose.yml and just type:


docker-compose up -d --build

docker-compose down

docker-compose up -d

# check servers
localhost:8081 webserver

localhost:8082 adminer(to view and manage database)

localhost:8083 Fake SMTP Email(to debug emails)

# get elasticsearch status: 
curl -XGET 'http://localhost:9200/_nodes/process'

curl -XGET 'localhost:9200/_cluster/health?pretty'


# Run command in docker image a way:
docker exec -it xone_web composer  update

# Enter in a docker image:
docker ps

docker exec -it 5032f265f6fa /bin/bash

////////////////
docker exec -it container-name/id command-to-run

dokcer exec -it contanoer-name /bin/bash
////////////////

# Check logs
docker logs --tail 50 --follow --timestamps container_id
docker-compose -f logs

# Kill container
docker kill container_id

# stop container
docker stop container_id

# remove container
 docker container rm container_name
