## docker-icecast2
Simple Dockerfile for running icecast2 in a container.
Just mount your icecast.xml file and you are good to go!

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
