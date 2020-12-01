# docker

1. how to search a docker image in hub.docker.com
>>- docker search httpd

2. Download a docker image from hub.docker.com
>>- docker image pull <image_name>:<image_version/tag>

3. List out docker images from your local system
>>- docker image ls

4. Create/run/start a docker container from image
>>- docker run -d --name <container_Name> <image_name>:<image_version/tag>

>>- d - run your container in back ground (detached)

5. Expose your application to host server
>>- docker run -d  -p <host_port>:<container_port> --name <container_Name> <image_name>:<Image_version/tag>

>>- docker run -d -p 8080:80 -p 3000:80 --name starwars httpd:2.3

**if the above command isn't working use the following**
>>- docker run -d --restart unless-stopped -p <host_port>:<container_port> --name <container_Name> <image_name>:<Image_version/tag>

>>- EXAMPLE: docker run -d --name httpd_server -p 8080:80 httpd:2.2
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

11. Remove a container (Can not remove a running container)
>>- docker rm <container_id>

12. login to a docker container
>>- docker exec -it <container_Name> /bin/bash

13. Pull only Container Ids
>>- docker ps -aq

14. Delete multiple containers
>>- docker rm $(docker ps -aq)
>>- docker rm $(docker images -aq)

15. Format Container
>>- docker ps --format="ID\t{{.ID}}\nNAME\t{{.Names}}\nIMAGE\t{{.Image}}\nPORTS\t{{.Ports}}\nCOMMAND\t{{.Command}}\nCREATED\t{{.CreatedAt}}\nSTATUS\t{{.Status}}\n"

16. Run Dockerfile to create image (Dockerfile - Contains a series of steps that define how your image is build.)
>>- docker build . -t httpd:latest
>>- "t" tag

17. Docker run 
>>- docker run -p 8080:8080 httpd:latest

18. Docker Volumes (allow sharing of data between files, folders & containers)
>>- (example to share files between local and container run) docker run -d --name website -v $(pwd):/usr/share/nginx/html:ro -p 8080:80 nginx:latest
>>>- "ro" read only. If we want to write then we need to remove "ro"

>>- (example to share files between containers) 
>>- docker run -d --name website-copy --volumes-from website -p 8081:80 nginx

