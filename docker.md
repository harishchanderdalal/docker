# Docker CMD
Check Docker Version
```
sudo docker version
```
Docker Complete information
```
sudo docker info
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
```
Help for docker container
```
sudo docker container --help
```


## Start Container
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
