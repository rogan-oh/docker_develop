# docker_develop
1. nginx 빌드 및 실행

1) nginx 디렉토리 이동
(base) [omh@omh ~]$ cd docker_develop/nginx/

2) ngix 경로 확인
(base) [omh@omh nginx]$ pwd
/home/omh/docker_develop/nginx

3) dockerfile build
(base) [omh@omh nginx]$ docker build -t nginx:0.1 ./

4) docker 이미지 확인
(base) [omh@omh nginx]$ docker images
REPOSITORY                 TAG                 IMAGE ID            CREATED             SIZE
nginx                      0.1                 d1e11f684499        5 seconds ago       166

5) docker container 실행
(base) [omh@omh nginx]$ docker run -it -p 8080:80 -d nginx:0.1 /bin/bash
ab4e3e623fc20e5c32d376d12549801711ef98fde7cfea4091e7acd2c2ed4d3b

6) docker container 접속
(base) [omh@omh nginx]$ docker exec -it ab4e3e623fc2 /bin/bash

7) nginx 실행 확인
###nginx 실행까지 3분정도 소요
root@ab4e3e623fc2:/var/log/nginx# service nginx status
 * nginx is running

