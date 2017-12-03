# Docker CMD
- sudo docker version
- sudo docker info

- start container
```
* Run Container
sudo docker container run --publish 80:80 nginx
sudo docker container run --publish 80:80 --detach nginx
sudo docker container ls
sudo docker container stop 67cc
sudo docker container ls -a

sudo docker container run --publish 80:80 --detach --name frontend nginx
sudo docker container logs frontend
sudo docker container top frontend

sudo docker container rm id id id id
sudo docker container rm -f id

sudo docker container --help
```
