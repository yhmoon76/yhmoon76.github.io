---
title: Docker
author: WooYou
date: 2022-03-28
category: docker
layout: post
isMenu: true
---
# [Docker][Docker_url]

[Docker_url]: https://www.docker.com/

[docker hub][docker_hub_url] yhmoon76/!ansdydgh12

[docker_hub_url]: https://hub.docker.com/

[docker doc][docker_doc_url]

[docker_doc_url]: https://docs.docker.com/desktop/



[Moby Project][Moby_Project_url]

[Moby_Project_url]: https://mobyproject.org/

* Docker Engine (Docker의 핵심 기능)
* Docker Registry (이미지 공개 및 공유)
* Docker Compose (컨테어너 일원 관리)
* Docker Machine (Docker 실행 환경 구축)
* Docker Swarm (클러스터 관리)


## Docker 설치
### [Docker Desktop for Windows] [Docker_Desktop_for_Windows_url]

[Docker_Desktop_for_Windows_url]: https://hub.docker.com/editions/community/docker-ce-desktop-windows

* [설치파일][설치파일_url]
* 설치파일로 설치후 윈도우 검색으로 'windows 기능  켜기/끄기' 에서 Hyper-V 항목 체크 후 윈도우 리부팅
* Hello word 출력
    <pre>
    docker container run ubuntu:latest /bin/echo 'Hello world'
    </pre> 

[설치파일_url]: 99_install/Docker_Desktop_Installer

## Docker 명령어
* docker version
* docker system info
* docker system df
* Nginx 설치
    <pre>
    == 설치 == 
    $ docker pull nginx  

    == 설치 확인 == 
    $ docker image ls 

    == 이미지를 사용하여 Nginx 서버 가동 == 
    $ docker container run --name webserver -d -p 80:80 nginx

    == 실행 확인 == 
    $ docker container ps 
    $ docker container stats webserver 

    == 실행 종료 == 
    $ docker stop webserver 

    == 컨테이너 가동 == 
    $ docker start webserver 

  </pre>

* docker image pull 명령
    <pre>
    == 기본 == 
    $ docker image pull [옵션] 이미지명[:태그명] 

    == CentOS의 이미지 취득 == 
    $ docker image pull centos:7

    == CentOS의 모든 태그 이미지 취득 == 
    $ docker image pull -a centos 

    == 오픈소스 기계학습용 프레임워크인 Tensorflow 의 Docker 이미지를 'https://gcr.io.tensorflow/tensorflow' 로부터 취득 == 
    $ docker image pull gcr.io.tensorflow/tensorflow

    == 기본 == 
    $ docker image pull [옵션] 이미지명[:태그명]
    </pre>

* 이미지 목록 표시

  <pre>
  == docker image ls 명령 == 
  $ docker image ls [옵션] [리포지토리명] 

  $ docker image ls
  REPOSITORY   TAG       IMAGE ID       CREATED        SIZE
  nginx        latest    605c77e624dd   6 days ago     141MB
  alpine/git   latest    c6b70534b534   6 weeks ago    27.4MB
  ubuntu       latest    ba6acccedd29   2 months ago   72.8MB

  REPOSITORY : 이미지 이름
  TAG : 이미지 태그명
  IMAGE ID : 이미지 ID
  CREATED : 작성일
  SIZE : 이미지 크기

  $ docker image ls --digests nginx
  REPOSITORY   TAG       DIGEST                                                                    IMAGE ID       CREATED      SIZE
  nginx        latest    sha256:0d17b565c37bcbd895e9d92315a05c1c3c9a29f762b011a10c54a66cd53c9b31   605c77e624dd   6 days ago   141MB

  이미지 상세 정보 확인
  $ docker image inspect nginx
  [
    {
        "Id": "sha256:605c77e624ddb75e6110f997c58876baa13f8754486b461117934b24a9dc3a85",
        "RepoTags": [
            "nginx:latest"
        ],
        "RepoDigests": [
            "nginx@sha256:0d17b565c37bcbd895e9d92315a05c1c3c9a29f762b011a10c54a66cd53c9b31"
        ...

  $ docker image inspect --format="{{ .RepoTags}}" nginx
  [nginx:latest]

  $ docker image inspect --format="{{ .Config.AttachStdout}}" nginx
  false
  </pre>  

* 이미지 태그 설정
  <pre>
  $ docker image ls
  REPOSITORY              TAG       IMAGE ID       CREATED        SIZE
  nginx                   latest    605c77e624dd   6 days ago     141MB
  alpine/git              latest    c6b70534b534   6 weeks ago    27.4MB
  ubuntu                  latest    ba6acccedd29   2 months ago   72.8MB
  centos                  7         eeb6ee3f44bd   3 months ago   204MB
  asashiho/dockersample   latest    6d041c204453   2 years ago    319MB


  $ docker image tag nginx yhmoon76/webserver:1.0

  $ docker image ls
  REPOSITORY              TAG       IMAGE ID       CREATED        SIZE
  nginx                   latest    605c77e624dd   6 days ago     141MB
  yhmoon76/webserver      1.0       605c77e624dd   6 days ago     141MB
  alpine/git              latest    c6b70534b534   6 weeks ago    27.4MB
  ubuntu                  latest    ba6acccedd29   2 months ago   72.8MB
  centos                  7         eeb6ee3f44bd   3 months ago   204MB
  asashiho/dockersample   latest    6d041c204453   2 years ago    319MB
  </pre>

* 이미지 검색
  <pre>
  Docker Hub에 공개되어 있는 이미지 검색
  $ docker search [옵션] &lt;검색 키워드&gt;

  $ docker search nginx
  NAME                              DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
  nginx                             Official build of Nginx.                        16071     [OK]
  ...

  NAME : 이미지 이름
  DESCRIPTION : 이미지 설명
  STARS : 즐겨찾기 수
  OFFICIAL : 공식 이미지인지 아닌지
  AUTOMATED : Dockerfile을 바탕으로 자동 생성된 이미지인지 아닌지 

  stars의 건수가 1000건 이상인 이미지만 검색
  $ docker search --filter=stars=1000 nginx
  </pre>

* 이미지 삭제
  <pre>
  $ docker image rm [옵션] 이미지명 [이미지명]

  사용하지 않는 이미지를 모두 삭제
  $ docker image prune -a
  </pre>

* 이미지 업로드
  <pre>
  $ docker image push 이미지명[:태그명]

  $ docker image push yhmoon76/webserver:1.0
  </pre>

* 컨테이저 라이프 사이클
  <pre>
  * 컨테이너 생성 (docker container create 명령)

  * 컨테이너 생성 및 시작 (docker container run 명령)
    $ docker container run [실행 옵션] 이미지명[:태그명] [인수]

    $ docker container run -it --name "test1" centos /bin/cal

      docker container run : 컨테이너를 생성 및 실행
      -it                  : 콘솔에 결과를 출력하는 옵션
      --name "test1"       : 컨테이너명
      centos               : 이미지명
      /bin/cal             : 컨테이너에서 실행할 명령


    $ docker container run -d centos /bin/ping localhost

      docker container run : 컨테이너를 생성 및 실행
      -d                   : 백그라운드에서 실행하는 옵션
      centos               : 이미지명
      /bin/ping localhost  : 컨테이너에서 실행할 명령

    백그라운드 로그 확인
    $ docker container ps
      CONTAINER ID   IMAGE     COMMAND                 CREATED              STATUS              PORTS     NAMES
      fa1eba180cf8   centos    "/bin/ping localhost"   About a minute ago   Up About a minute             musing_lichterman
    
    $ docker container logs -t fa1eba180cf8 

  * 컨테이너 시작 (docker container start 명령)
    
  * 컨테이너 재시작 (docker container restart 명령)

  * 컨테이너 정지 (docker container stop 명령)

  * 컨테이너 삭제 (docker container rm 명령)

  </pre>


## 단어
* 온프레미스 : 자사에서 데이타센터를 보유하고 시스템 구축부터 운용까지를 모두 수행하는 형태
* 오케스트레이션 : 