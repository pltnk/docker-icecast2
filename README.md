## docker-icecast2

[![Build Status](https://img.shields.io/github/actions/workflow/status/pltnk/docker-icecast2/docker-publish.yml?branch=main)](https://github.com/pltnk/docker-icecast2/actions/workflows/docker-publish.yml)
[![Docker Pulls](https://img.shields.io/docker/pulls/pltnk/icecast2)](https://hub.docker.com/r/pltnk/icecast2)
[![Docker Image Size](https://img.shields.io/docker/image-size/pltnk/icecast2/latest)](https://hub.docker.com/r/pltnk/icecast2)
[![License](https://img.shields.io/github/license/pltnk/docker-icecast2)](https://github.com/pltnk/docker-icecast2/blob/master/LICENSE)

Simple Dockerfile for running [icecast2](https://icecast.org/) in a container. \
Just mount your icecast.xml file and you are good to go!

Works well with containerized [Liquidsoap](https://www.liquidsoap.info/): [pltnk/docker-liquidsoap](https://github.com/pltnk/docker-liquidsoap)

### Installation
- Pull the image from one of public Docker registries
  - Docker Hub `docker pull pltnk/icecast2`
  - GitHub Packages `docker pull ghcr.io/pltnk/icecast2`
  - Quay.io `docker pull quay.io/pltnk/icecast2`
- Build the image yourself
  - `docker build -t pltnk/icecast2 github.com/pltnk/docker-icecast2`

### Configuration
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
