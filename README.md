## docker-icecast2
Simple Dockerfile for running [icecast2](https://icecast.org/) in a container. \
Just mount your icecast.xml file and you are good to go!

### Installation:
You can either pull the image from Dockerhub \
```docker pull pltnk/icecast2``` \
or build it yourself \
```docker build -t pltnk/icecast2 github.com/pltnk/docker-icecast2```

### Configuration:

#### docker run
```
docker run --name icecast2 -d --restart=always \
--publish 8000:8000 \
--volume /path/to/your/icecast.xml:/etc/icecast2/icecast.xml \
pltnk/icecast2
```
#### docker-compose.yml
```
icecast2:
  image: pltnk/icecast2
  container_name: icecast2
  restart: always
  ports:
    - 8000:8000
  volumes:
    - /path/to/your/icecast.xml:/etc/icecast2/icecast.xml
```
