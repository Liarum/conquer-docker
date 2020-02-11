# conquer-docker
Docker를 정복해봅시다!

---

### Useful Command lines for using Docker

* create docker container

docker container create {{.image}} [option:command for container]

* run docker image

docker run -it —name “{{.name}” {{.image}} [option:command for container]

* stop running container

docker stop {{.container name | id}}

* delete docker container

docker rm {{.container name | id}}

* delete docker cached images

docker images —no-trunc —format ’{{.ID}}’ | xargs docker rmi

* start docker container

docker start {{container_name/Id}}

* run cli in bash

docker exec -it {{container_name/Id}} bash
