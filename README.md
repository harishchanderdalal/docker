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

#######################################################################################
#######################################################################################

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

# Swarm Configure

NOTE - Global Ports in Docker Swarm
Engine port: 2375
Secure Engine port: 2376
Swarm port: 2377

## Docker Installed in all machine which will react as worker or manager with Docker 1.12 or later
- Manger IP
1. 172.31.12.161
2. 172.31.12.162
3. 172.31.12.163

- Worker IP
1. 172.31.12.164
2. 172.31.12.165
3. 172.31.12.166

- IMP CMD
``` 
docker swarm join-token manager
docker swarm join-token worker
docker node ls
docker node promote (ID)
```

## Configure the Manager and Worker

- Manager 1
```
docker swarm init --advertise-addr 172.31.12.161:2377 --listen-addr 172.31.12.161:2377
```

- Manger 2
```
docker swarm join \
-- token foo \
172.31.12.161:2377
--advertise-addr 172.31.12.162:2377 \
--listen-addr 172.31.12.162:2377
```

- Manger 3
```
docker swarm join \
-- token foo \
172.31.12.161:2377
--advertise-addr 172.31.12.163:2377 \
--listen-addr 172.31.12.163:2377
```

- Worker 1
```
docker swarm join \
-- token foo \
172.31.12.161:2377
--advertise-addr 172.31.12.164:2377 \
--listen-addr 172.31.12.164:2377
```

- Worker 2
```
docker swarm join \
-- token foo \
172.31.12.161:2377
--advertise-addr 172.31.12.165:2377 \
--listen-addr 172.31.12.165:2377
```

- Worker 3
```
docker swarm join \
-- token foo \
172.31.12.161:2377
--advertise-addr 172.31.12.166:2377 \
--listen-addr 172.31.12.166:2377
```
#############################################################################################
## SWARM SERVICE
