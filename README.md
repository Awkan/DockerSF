# Docker SF

This docker job is to run a Symfony app (SF3.4 Flex or SF4).

It includes some containers
- NGINX
- php-fpm 7.1
- MariaDB
- PhpMyAdmin

# Installation

To use this docker, first download it
```bash
git@github.com:Awkan/DockerSF.git
```

These files should be moved to your Symfony app (at root dir).
Now your Symfony app got a docker configuration.

Then you just have to use the `docker-compose.yaml` file.
```bash
# Build images
docker-compose build
# Start containers
docker-compose up -d
```
