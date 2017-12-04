## Installation on UBUNTU
```
sudo apt-get -y install docker.io
curl -sSL https://get.docker.com/ | sh
sudo usermod -aG docker vagrant
sudo docker version
```
```
curl -L https://github.com/docker/machine/releases/download/v0.13.0/docker-machine-`uname -s`-`uname -m` >/tmp/docker-machine && chmod +x /tmp/docker-machine && sudo cp /tmp/docker-machine /usr/local/bin/docker-machine
docker-machine version
```
```
sudo curl -L https://github.com/docker/compose/releases/download/1.17.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

# Docker CMD
Check Docker Version
```
sudo docker version
```
Docker Complete information
```
sudo docker info
```
Docker images
```
sudo docker image ls
```
List Running Container
```
sudo docker container ls
```
List All Container
```
sudo docker container ls -a
```
How to stop Container
```
sudo docker container stop 67cc
```
How to remove docker Container
```
sudo docker container rm id id id id
```
How to remove docker Container Forcefully
```
sudo docker container rm -f id
```
How check logs of foreground container
```
sudo docker container logs frontend
```
How to check top of foreground container
```
sudo docker container top frontend
sudo docker container port frontend
```
Help for docker container
```
sudo docker container --help
sudo docker container stats
- sudo docker container inspect name
  sudo docker container inspect --format '{{ .NetworkSettings.IPAddress }}' webserver
```


## Container
Run Container Simple
```
sudo docker container run --publish 80:80 nginx
```
Run Container IT
```
sudo docker container run -it --name proxy nginx bash
sudo docker container run -it --name ubuntu ubuntu
sudo docker container exec -it db bash
```
Run Container Simple
```
sudo docker container run --publish 80:80 nginx
```
Run Container as Foreground
```
sudo docker container run --publish 80:80 --detach nginx
```
Run Container as Foreground with name
```
sudo docker container run --publish 80:80 --detach --name frontend nginx
```
Run Container as Foreground with name with cmd
```
sudo docker container run --publish 80:80 --detach --name frontend nginx nginx -T
```
Run Container as Foreground with name with cmd with env
```
sudo docker container run --publish 3306:3306 --detach --name db -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
```


## Network
Run Container Simple
```
sudo docker network ls
sudo docker network inspect
sudo docker network inspect bridge
sudo docker network craete --driver
sudo docker network connect
sudo docker network disconnect
```

### Create Network
```
sudo docker network create app
sudo docker network create --help
sudo docker container run --publish 8080:80 -d --name app2 --network apps httpd

sudo docker container run -d --name try1 --net apps --net-alias harish.ccom elasticsearch:2
sudo docker container run --rm --net apps alpine nslookup harish.com
```
