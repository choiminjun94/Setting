# 0522

## Docker Install

URL : https://www.docker.com/

### 자기 환경에 맞는 도커 다운

![스크린샷 2023-05-22 오후 8 15 00](https://github.com/choiminjun94/Setting/assets/60457431/89c27a2b-1afd-4de0-9540-e0f60fd7b5ee)

## 설치

![스크린샷 2023-05-22 오후 8 14 31](https://github.com/choiminjun94/Setting/assets/60457431/88b0f23d-5407-4276-ae33-da71ca2a25b9)
![스크린샷 2023-05-22 오후 8 21 03](https://github.com/choiminjun94/Setting/assets/60457431/e15f9b29-b388-4968-bb42-4bcdb8d42a9a)

## 오라클 설치

### 도커 설치 확인

```txt

docker

```

![스크린샷 2023-05-22 오후 8 24 02](https://github.com/choiminjun94/Setting/assets/60457431/8e287fbb-896f-4862-a976-7756c99ab090)

### 도커 로그인

```sql

미리 도커에 가입을 진행 한다.

docker login

usernaem : 자기 계정 입력
password : 자기 계정 비번 입력

```

![스크린샷 2023-05-23 오전 7 55 38](https://github.com/choiminjun94/Setting/assets/60457431/5ba0655a-0839-45a0-9a97-97004c1908ff)

### oracle seacrh 및 설치

```sql

docker search oracle-xe-11g

```

![스크린샷 2023-05-23 오전 7 57 19](https://github.com/choiminjun94/Setting/assets/60457431/c7e4eb4b-56e8-4f68-9603-5589c16f7508)

```sql

docker pull jaspeen/oracle-xe-11g

```

![스크린샷 2023-05-23 오전 7 58 36](https://github.com/choiminjun94/Setting/assets/60457431/9e9e7e28-2761-4a47-81f0-044d21e207a0)

도커 컨테이너 생성

```sql

docker run -d --name [컨테이너이름] -p [localhost포트]:1521 [oracle-image-name]
docker run --name oracle11g -d -p 8080:8080 -p 1521:1521 jaspeen/oracle-xe-11g

```

![스크린샷 2023-05-23 오전 8 01 38](https://github.com/choiminjun94/Setting/assets/60457431/6762bc8c-4898-409c-9fb9-f6639557cc72)

## 디비버 연결

```sql

Database : xe
UserName : system
Password : oracle

Test Connection > Download > 확인

```

![스크린샷 2023-05-23 오전 8 05 06](https://github.com/choiminjun94/Setting/assets/60457431/f5e6f694-326e-469f-a79e-91aee46e0257)

![스크린샷 2023-05-22 오후 8 34 30](https://github.com/choiminjun94/Setting/assets/60457431/d2def9c0-aed8-41d5-826e-3f68b24457d3)

![스크린샷 2023-05-23 오전 8 05 20](https://github.com/choiminjun94/Setting/assets/60457431/f340c68e-1150-4c3f-8018-1086da2d0e7b)

## 계정 생성 및 권한 부여

### 계정 생성

```sql

create user 아이디 identified by 비번;

create user scott identified by tiger;

```

### 권한 부여

```sql

grant 권한 to id;
grant connect, resource, dba to 아이디;

```

### 변경사항 저장

```sql

commit;

```

### 계정 생성 확인

```sql

select * from all_users;

```

![스크린샷 2023-05-23 오후 2 20 25](https://github.com/choiminjun94/Setting/assets/60457431/3b0766fb-6e8a-4210-91e9-c8594aa324c6)
