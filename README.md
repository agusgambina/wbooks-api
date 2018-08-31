# WBooks API

This project has learning and practicing purposes.

## Docker

There are two alternatives, to run postgres in a container, or set up as a service. In the first option, no matter what happens, everything will be lost when the container is destroyed. In the second option the data will be isolated in a volume and data will be persisted.

### Setup PostgresSQL in a container

```
$ docker run --name wbooks-postgres -p 5432:5432 -e POSTGRES_USER=wbooks-api -e POSTGRES_PASSWORD=wbooks-api -e POSTGRES_DB=wbooks-api_development -d postgres:11
```

### Setup PostgresSQL as a service in Swarm

1. `$ docker swarm init`
2. `$ docker network create --driver overlay wbooks_backend_network`
3. `$ mkdir -p ~/docker/volumes/wbooks-api_development`
4. `$ docker stack deploy -c docker/docker-compose.yml wbooks`

## Resources

* [WBooks API - Apiary](https://wbooksapi.docs.apiary.io/)
