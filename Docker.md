**Docker**



Feature

- 이미지 생성과 배포에 특화
- 이미지 버전관리, 중앙 저장소에 이미지를 올리고 받을 수 있음
- Github와 비슷한 형태
- 다양한 API 제공, 자동화 가능
- DevOps

이미지

- 서비스 운영에 필요한 프로그램, 소스 코드, 컴파일ㄷ뇌 실행 파일을 묶은 형태
- 저장소에 올리고 받는건 **이미지**



컨테이너

- 이미지를 **실행한 상태**
- 이미지로 **여러개의 컨테이너**를 만들 수있음

이미지는 실행파일, 컨테이너는 프로세스

유니온파일 형태



지금까지는 **물리 서버를 직접 운영*

-호스팅 or IDC코로케이션 서비스 사용



-도커 설치-

1. cd /etc/apt 들어가서 gedit sources.list 

2. deb https://apt.dockerproject.org/repo ubuntu-xenial main 로 설정

3. apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common      <-- https 사용 가능하게 만들기

4. apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D

5. apt-get install linux-image-extra-$(uname -r)

6. apt-get update
7. apt-get install docker-engine
8. apt-get install golang.go





  301  gedit main.go
  302  cd docker.
  303  cd docker
  304  gedit main.go
  305  cd docker
  306  gedit Dockerfile
  307  ls
  308  docker image build -t example/echo:latest .
  309  docker image ls
  310  docker image ls0k
  311  docker image ls -a
  312  gdeit main.go
  313  gedit main.go
  314  docker image build -t example/echo:latest .
  315  docker image ls
  316  docker image ls -a
  317  docker container run -p 9000:8080 -d example/echo:latest
  318  docker container ls
  319  docker container ps
  320  docker container run -p 9001:8080 -d example/echo:latest
  321  docker container ls
  322  docker container rm 7a
  323  docker container rm -f 7a
  324  docker container ps
  325  docker container rm -f 0c
  326  docker container ps
  327  docker container run -p 9000:8080 -d example/echo:latest
  328  docker container run -p 9001:8080 -d example/echo:latest
  329  docker container ps
  330  comainser ps -q
  331  docker container ps -q
  332  docker container rm -f $(docker container ps -q)
  333  docker container ps
  334  ls -l
  335  docker container run -it -p 9000:8080 -d example/echo:latest /bin/bash
  336  docker attach 44b6
  337  docker container ps
  338  docker container ps -a
  339  docker contaimer restart 44b6
  340  docker container restart 44b6
  341  docker container ps -a
  342  docker container stop 44b6
  343  docker container ps -a
  344  docker container run -it -p 9000:8080 --name echo1 -d example/echo:latest
  345  docker container ps -a
  346  docker container run -it -p 9001:8080 --name echo2 -d example/echo:latest
  347  docker container ps
  348  docker container run -p 9002:80 --name web1 nginx
  349  docker container ps -a
  350  docker container run -p 9003:80 -d --name web2 nginx
  351  docker container ps
  352  docker container ps -a
  353  docker container ps --filter "ancestor=example/echo"
  354  docker container ps -a --filter "ancestor=example/echo" 
  355  docker container ps -a --filter "ancestor=example/echo"  -a
  356  docker container rm $(docker container ps -a "ancestor=example/echo") 
  357  docker container rm -f $(docker container ps -a "ancestor=example/echo") 
  358  docker container rm -f $(docker container ps -a --filter "ancestor=example/echo") 
  359  docker container ps
  360  docker container rm -f $(docker container ps -a --filter "ancestor=example/echo") 
  361  docker container rm -f $(docker container ps --filter "ancestor=example/echo") 



-도커 지우기-

 430  docker container exec f08f ls /usr/share/nginx/html/
  431  docker container rm -f $(docker container ls -a -q)
  432  docker image rm $(docker image ls -q)
  433  docker image rm -f $(docker image ls -q)
  434  docker system prune



-도커 컨테이너문서를 꺼냈다 다시 넣기-

root@server:~/docker# docker container exec e250 ls /usr/share/nginx/html
50x.html
index.html
root@server:~/docker# docker container cp e250:/usr/share/nginx/html/index.html .
root@server:~/docker# ls
Dockerfile  index.html  main.go
root@server:~/docker# gedit index.html
root@server:~/docker# docker container cp ./index.html e250:/usr/share/nginx/html/index.html 
root@server:~/docker# 









*Docker*

image build :docker 파일 생성

image pull: 이미지를 가져옴 - 이미지 이름 필요

image push: 이름은 unique 해야함 



container run :실행 , image 이름 들어가야함
-d, -it,-p, --name 많이 사용함





