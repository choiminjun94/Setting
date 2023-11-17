# Oracle 맥 실리콘 설치

## homebrew install 

 먼저 homebrew를 먼저 설치 해야 한다. 

``` sql 

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

```

## docker install 

사진 추가 

``` sql

brew install docker

```

설치 이후 확인을 위해 아래의 명령어를 검색  
컨테이너 리스트를 반환해주는 명령어

사진 추가

``` sql 

docker ps 

```


## colima install

M1 맥북에서는 CPU 아키텍쳐가 달라 오라클 컨테이너가 생성이 되지 않았다.

그래서 찾은 방법이 M1 맥북에서 x86_64(intel 아키텍처)로 사용하는 방법이 있다

colima라는 오픈소스 라이브러리를 설치하는 것이다.

사진 추가

```sql 

brew install colima

```

설치하는데 생각보다 시간이 오래 걸린다. 

사진 추가

### colima 시작

``` sql 

colima start --arch x86_64 --cpu 4 --memory 8 

```

## Oracle 설치 

Oracle Database 11gR2 XE (11.2.0.2) 설치

사진 추가

``` sql 

docker search oracle-xe-11g 

```

사진 추가

``` sql 

docker pull jaspeen/oracle-xe-11g

```

오라클 서버를 띄우는 명령어로 PASSWORD="각자 원하는 비밀번호"로 옵션을 변경

사진 추가

``` sql 

docker run -e ORACLE_PASSWORD=비번 -p 1521:1521 -d gvenzl/oracle-xe

```


