# docker

1. how to search a docker image in hub.docker.com
>>- docker search httpd
2. Download a docker image from hub.docker.com
>>- docker i>>- mage pull <image_name>:<image_version/tag>
3. List out docker images from your local system
>>- docker image ls
4. Create/run/start a docker container from image
>>- docker run -d --name <container_Name> <image_name>:<image_version/tag>

>>- d - run your container in back ground (detached)
5. Expose your application to host server
>>- docker run -d  -p <host_port>:<container_port> --name <container_Name> <image_name>:<Image_version/tag>

>>- docker run -d --name httpd_server -p 8080:80 httpd:2.2
6. List out running containers
>>- docker ps
7. List out all docker container (running, stpooed, terminated, etc...)
>>- docker ps -a
8. run a OS based container which interactive mode (nothing but login to container after it is up and running)
>>- docker run -i -t --name centos_server centos:latest
>>- i - interactive
>>- t - Terminal
9. Stop a container
>>- docker stop <container_id>
10. Start a container which is in stopped or exit state
>>- docker start <container_id>
11. Remove a container
>>- docker rm <container_id>
12. login to a docker container
>>- docker exec -it <container_Name> /bin/bash
