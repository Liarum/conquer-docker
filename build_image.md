# How to Docker Image Build

도커 컨테이너를 커밋하여 이미지로 만든 뒤 작업 환경을 구축할 때 유용하게 쓸 수 있다.

Docker Hub를 통해 배포도 가능!



`docker commit CONTAINER_ID/NAME`



---

#### Develop Log : 2020-02-17

- LAMP 환경이 구축된 이미지로 -v -p 옵션을 주어 로컬에서 도커 컨테이너에 공유 폴더와 MySql 서버에 접근할 수 있었다.
  - -v : volume mount 옵션으로 로컬과 도커 컨테이너의 공유 폴더를 만들어서 로컬의 텍스트 편집기로 컨테이너의 소스를 편집할 때나, 용량이 큰 자원을 공유할 때 유용하게 사용할 수 있다.
  - -p : port forwarding 옵션