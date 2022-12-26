## Instructions

## docker hello world
-- docker clear
-- docker run hello-world
-- docker ps = show all containers active
-- docker ps -a = show all containers

## docker install ubuntu
-- docker run -it ubuntu bash
-- -it = attach terminal and keep (interactive module)
-- docker run -it --rm ubuntu bash = emove container after run

## docker install nginx
-- docker run nginx
-- docker run -p 8080:80 nginx = port forwarding(publish the port)(-p)
-- docker run -d -p 8080:80 nginx = unbinding the terminal from the process(-d)
-- docker start container id = start container by id
-- docker stop container id = stop container by id
-- docker rm container id or docker rm container id -f = remove container by id or force remove

## Accessing and changing files in a container
-- docker run --name nginx -d -p 8080:80 nginx = rename container(--name)
-- docker exec = execute command in container 
-- docker exec nginx ls = execute command ls(list the directory)
-- docker exec nginx bash
-- docker exec -it nginx bash
    -- cd /usr/share/nginx/html/ 
    -- apt-get update = get all images for install
    -- apt-get install vim = install vim in container

## Starting with bind mounts
-- docker run --name nginx -d -p 8080:80 -v ~/fullcycle/fullcycle-docker/bind_mounts:/usr/share/nginx/html nginx= mount a volume(-v)
-- docker run -d --name nginx -p 8080:80 --mount type=bind, source="$(pwd)"/bind_mounts, target=/usr/share/nginx/html nginx

## Create volume
-- docker volume create myvolume
-- docker volume ls
-- docker volume inspect myvolume
-- docker volume prune

## Understanding images and DockerHub
-- docker rmi nginx:latest = remove image

## Create my first image docker
-- docker build -t gladstone-thiago/nginx-with-vim:latest .
-- docker run -it gladstone-thiago/nginx-with-vim bash

## Delete all containers
-- docker rm $(docker ps -a -q) -f

## ENTRYPOINT vs CMD
1.0 Replace CMD
-- docker run -rm  gladstone-thiago/hello echo "oi"