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
-- docker run -p 8080:80 nginx = port forwarding(publish the port)
-- docker run -d -p 8080:80 nginx = unbinding the terminal from the process
-- docker start container id = start container by id
-- docker stop container id = stop container by id
-- docker rm container id or docker rm container id -f = remove container by id or force remove