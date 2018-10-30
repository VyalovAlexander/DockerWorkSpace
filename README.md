# DockerWorkSpace

## Run

```terminal

docker-compose up -d

```

# How it works

Each service has it own directory in ./docker folder, there you can find:

* Dockerfile
* docker-command.sh - file is copied to container while building, you can write bash commands inside it (do not forget to uncomment '#command: sh /docker-command.sh' in docker-compose.yml)
* logs in log directory
* db data in data directory
* other useful files, which are needed by service

Also you have .env file, inside it you can find ENV variables and arguments:

* POSTGRES_DB - database name in postgres
* POSTGRES_PASSWORD - database password
* POSTGRES_USER - database user
* NGINX_HTTP_EXTERNAL_PORT - external port for http connections 
* NGINX_HTTPS_EXTERNAL_PORT - external port for https connections
* POSTGRES_EXTERNAL_PORT - external port for postgres, for db GUI clients
* REDIS_EXTERNAL_PORT - external port for redis, for redis GUI clients
* XDEBUG_REMOTE_HOST - ip of your machine for xdebug (mostly unused because option "xdebug.remote_connect_back" is set to "1" in php Dockerfile)
* XDEBUG_REMOTE_PORT - xdebug remote port, if you are using PHPStorm just change "debug port" in settings -> Languages & Frameworks -> PHP -> Debug