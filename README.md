# Docker

## How to install
```
curl --version
curl -sSL https://get.docker.com/ | sh
systemctl enable docker
systemctl start docker
docker run hello-world
docker ps -a
```

wget -q0- https://get.docker.com/ | sh

## Docker Handy Cmd
```
sudo docker version
sudo docker info
sudo docker run hello-world
sudo docker ps
sudo docker ps -a (exited contanier)
```

#############################################################################################
#############################################################################################

# CONTAINERS

## Docker hub
- hub.docker.com

## What is Containers and images
- images = stopped containers
- containers = running images

## How to Download Docker Image few example
```
sudo docker pull alpine
sudo docker pull ubuntu
sudo docker pull ubuntu:14.04
```

## List all the images
```
sudo docker images
```

## Delete the download image from local
```
sudo docker rmi ubuntu:14.04
```

## Start docker with foreground service and name specify
```
sudo docker run -d --name web -p 80:8080 nginx
```
- start and stop web container
```
sudo docker stop web
sudo docker start web
```

## login in you container with intreactive mode
```
sudo docker run -it --name try ubuntu:latest /bin/bash
```
- Exit from intreactive mode without stop
```
CTRL P+Q
```

## Stop and start multiple imgaes containers
```
sudo docker stop $(docker ps -aq)
sudo docker rm $(docker ps -aq)
sudo docker rmi $(docker images -q)
```

#############################################################################################
#############################################################################################

## SWARM
