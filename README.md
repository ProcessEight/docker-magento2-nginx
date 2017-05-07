# Docker Magento 2 Nginx

## Description

A proof-of-concept image which installs Nginx with the default Magento 2 Nginx server config.
This image is built from the [official Nginx image](https://hub.docker.com/_/nginx/). 

## Variables

The following environment variables are used for Nginx configuration:

- `PHP_HOST`: (default: `phpfpm`) The hostname of the PHP container.
- `PHP_PORT`: (default: `9000`) The port of the PHP container.
- `APP_MAGE_MODE`: (default: `developer`) Set the appropriate MAGE_MODE.

The `bin/start.sh` script uses `sed` to substitute environment variables for those defined in the `Dockerfile`.

## Building it

Run the `build` command to build the image:

```bash
$ docker build -f Dockerfile -t projecteight/nginx-1.11:0.1.0 -t projecteight/nginx-1.11:latest .
$ docker images
REPOSITORY                   TAG                 IMAGE ID            CREATED             SIZE
projecteight/nginx-1.11      0.1.0               d449940aa399        About an hour ago   183 MB
projecteight/nginx-1.11      latest              d449940aa399        About an hour ago   183 MB
...
```

## Using it

This image is intended to be used with the [docker-magento2-compose](https://github.com/projecteight/docker-magento2-compose)  project
