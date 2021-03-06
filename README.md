## docker-icecast2

[![Travis CI Build Status](https://img.shields.io/travis/com/pltnk/docker-icecast2)](https://travis-ci.com/github/pltnk/docker-icecast2)
[![Docker Image Size](https://img.shields.io/docker/image-size/pltnk/icecast2)](https://hub.docker.com/r/pltnk/icecast2)
[![Docker Pulls](https://img.shields.io/docker/pulls/pltnk/icecast2)](https://hub.docker.com/r/pltnk/icecast2)
[![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/pltnk/icecast2)](https://hub.docker.com/r/pltnk/icecast2)
[![License](https://img.shields.io/github/license/pltnk/docker-icecast2)](https://github.com/pltnk/docker-icecast2/blob/master/LICENSE)

Simple Dockerfile for running [icecast2](https://icecast.org/) in a container. \
Just mount your icecast.xml file and you are good to go!

Works well with containerized [Liquidsoap](https://www.liquidsoap.info/): [pltnk/docker-liquidsoap](https://github.com/pltnk/docker-liquidsoap)

### Installation:
You can either pull the image from Dockerhub \
`docker pull pltnk/icecast2` \
or build it yourself \
`docker build -t pltnk/icecast2 github.com/pltnk/docker-icecast2`

### Configuration:
- Mount your icecast.xml to `/etc/icecast2/icecast.xml`
- Publish necessary ports

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
