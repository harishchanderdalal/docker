# Node js With Docker

This will create the sample for docker with nodejs

## Steps

```bash
git clone https://github.com/harishchanderdalal/docker.git
cd docker
git checkout -b origin/nodejs
docker build -t lab/nodeweb .
docker run -p 80:8080 -d lab/nodeweb
docker container ps
curl -i localhost
```

```bash
git clone https://github.com/harishchanderdalal/docker.git
cd docker
git checkout -b origin/nodejs
docker build -t lab/nodeweb .
docker run -p 80:8080 -d lab/nodeweb
docker container ps
curl -i localhost
```
### Allow 80 Port Azure InBound and Open with Public IP in Browser
