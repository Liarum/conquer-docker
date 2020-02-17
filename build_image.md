# How to Docker Image Build

도커 컨테이너를 커밋하여 이미지로 만든 뒤 작업 환경을 구축할 때 유용하게 쓸 수 있다.

Docker Hub를 통해 배포도 가능!



`docker commit CONTAINER_ID/NAME NEW_IMAGE_NAME`
(-m : commit message 옵션 사용 가능)


---

#### Develop Log : 2020-02-17

- LAMP 환경이 구축된 이미지로 -v -p 옵션을 주어 로컬에서 도커 컨테이너에 공유 폴더와 MySql 서버에 접근할 수 있었다. 두 가지 옵션 모두 여러 개를 함께 줄 수 있다. (ex. docker run -p ... -p... -v... -v... 가능)  run 명령어를 쓸 때 -it IMAGE COMMAND 를 가장 나중에 붙여주어야 하는 이슈가 있었다.
  - -v : volume mount 옵션으로 로컬과 도커 컨테이너의 공유 폴더를 만들어서 로컬의 텍스트 편집기로 컨테이너의 소스를 편집할 때나, 용량이 큰 자원을 공유할 때 유용하게 사용할 수 있다.
    - 사용: docker run +  `-v LOCAL_DIR:CONTAINER_DIR`
  - -p : port forwarding 옵션, 도커 컨테이너의 포트와 로컬의 포트를 연결하여 사용하였다. Mysql 포트(보통 3306) 를 로컬의 포트와 포워딩하여 MySql 워크벤치로 컨테이너의 MySql 서버에 접근하여 작업을 편리하게 할 수 있었다. 또한 컨테이너에 구축한 Apache 서버의 가상 호스트의 포트와 포워딩하여 개발을 진행하였다.
    - 사용: docker run + -p `LOCAL_PORT:CONTAINER_PORT`

  
