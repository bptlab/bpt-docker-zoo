# BPT Docker Zoo - Easily deploy BPT applications all at once #

## Requirements ##

* Docker
* Docker Compose (version 3 at least)

## Configuration ##

* You can change the port where the whole system is reachable (default: 8080) in the `docker-compose.yml` file: Look at the proxy service and its specified port. Change the line `8080:80` to `port:80`.
* Even though the MySQL-server is not reachable to outside by default, you might want to change root password in the `docker-compose.yml` file (`MYSQL_ROOT_PASSWORD=...`). You also have to change the password for accessing Chimera und Unicorn (`CHIMERA_DB_PASSWORD=...` and `UNICORN_DB_PASSWORD=...`).

## Deployment ##

Run:

```
docker-compose up -d
```

Services are then reachable as (port may vary depending on configuration):

* http://localhost:8080/gryphon/
* http://localhost:8080/Unicorn/
* http://localhost:8080/Chimera/
