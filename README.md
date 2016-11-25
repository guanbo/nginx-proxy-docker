# Nginx Proxy Docker 

## Docker Compose

[Release](https://github.com/docker/compose/releases)

### Install

```zsh
$ sudo curl -L https://github.com/docker/compose/releases/download/1.9.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
```

## Quick Start

### Docker Network

```zsh
$ docker network create -d bridge nginx-proxy
```

### Startup

```zsh
$ docker-compose up -d
```

## Proxied app

```zsh
docker run \
  --name $CONTAINER -d \
  --env-file ./${NODE_ENV}.env \
  --network nginx-proxy \
  $IMAGE:$TAG
```