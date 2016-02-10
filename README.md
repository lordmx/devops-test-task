# App

Devops test task

## Install and run

Requirements:

* nodejs:latest
* mongodb:latest
* redis:latest

```
# install
npm i -production

# run (see server.js for env vars)
APP_SERVER_HOST=0.0.0.0 \
APP_SERVER_PORT=3000 \
APP_REDIS_URI=redis://docker.local:6380 \
APP_MONGO_URI=mongodb://docker.local:27117/app \
    node server.js
```

## Devops Task

1. Make Dockerfile for App
2. Make docker-compose.yml to set up whole environment (app, redis, mongo) + monitoring (influxdb + grafana + cadvisor)

You allowed to use redis, mongo, influxdb, grafana, cadvisor etc. images from [docker hub](https://hub.docker.com)

So, as result we expected to have Dockerfile, so it'll be possible to execute

```
docker build -t app .
docker run [... args and environment ..] --name=app app
```

and we expected to have some `docker-compose.yml` which allows us to do `docker-compose up` giving running App and it's monitoring tools