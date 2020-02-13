# conquer-docker
Docker를 정복해봅시다!

---

### Useful Command lines for using Docker

* create docker container

  docker container create {{.image}} [option:command for container]

* run docker image

  docker run -it —name “{{.name}” {{.image}} [option:command for container]

  * docker run options

  -p : 컨테이너와 호스트의 포트를 연결한다.

  --cpushare : cpu 스케쥴링 시 컨테이너의 비중을 늘린다.

  --name : 컨테이너의 이름을 설정한다.

  --volume : 호스트 OS와 컨테이너의 디렉터리를 공유한다.

  -d : 컨테이너를 detach 모드로 실행한다. 데몬모드로 실행한다고도 합니다.

  -i : 컨테이너와의 입출력을 interactive하게 설정한다.

  -t : 터미널 역할을 해주는 tty를 사용한다.

* stop running container

  docker stop {{.container name | id}}

* delete docker container

  docker rm {{.container name | id}}

* delete docker cached images

  docker images —no-trunc —format ’{{.ID}}’ | xargs docker rmi

* start docker container

  docker start {{container_name/Id}}

* run cli in bash

  docker exec -it {{container_name/Id}} /bin/bash

* show running container list
  docker ps
  (docker ps -a // all containers)

* run container with volumemount option
  docker run --name {{.container name}} -v {{.localVolumeDir}}:{{.sharedVolumeDir}} -it {{.image}} {{.cmd option}}
