# BPT Docker Zoo - Easily deploy BPT applications all at once #

## Requirements ##

* Docker
* Docker Compose (version 3 at least)

## Configuration ##

* You can change the port where the whole system is reachable (default: 8080) in the `docker-compose.yml` file: Look at the proxy service and its specified port. Change the line `8080:80` to `port:80`.
* You can change the location where the whole system is reachable (default: `/`) in the `host.env` file: Look at the environment variable `DEPLOY_PATH`. Also, you can change the names of deployed Chimera, Unicorn and Gryphon.
* Even though the MySQL-server is not reachable to outside by default, you might want to change root password in the `docker-compose.yml` file (`MYSQL_ROOT_PASSWORD=...`). You also have to change the password for accessing Chimera und Unicorn (`CHIMERA_DB_PASSWORD=...` and `UNICORN_DB_PASSWORD=...`).

## Deployment ##

Run:

```
docker-compose up -d
```

Services are then reachable as (port and locations may vary depending on configuration):

* http://localhost:8080/gryphon/
* http://localhost:8080/unicorn/
* http://localhost:8080/chimera/
