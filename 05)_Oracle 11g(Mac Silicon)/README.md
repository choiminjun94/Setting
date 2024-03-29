# 05)_Oracle 11g(Mac Silicon)

## homebrew install 

 먼저 homebrew를 먼저 설치 해야 한다. 

``` sql 

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

```

## docker install 

![1](https://github.com/choiminjun94/Setting/assets/60457431/c82f46b8-50c3-46ed-a1fe-82e960d2d51c)

``` sql

brew install docker

```

설치 이후 확인을 위해 아래의 명령어를 검색  
컨테이너 리스트를 반환해주는 명령어

![2](https://github.com/choiminjun94/Setting/assets/60457431/02743d4e-e681-4b89-801b-53020bcb4c53)

``` sql 

docker ps 

```


## colima install

M1 맥북에서는 CPU 아키텍쳐가 달라 오라클 컨테이너가 생성이 되지 않았다.

그래서 찾은 방법이 M1 맥북에서 x86_64(intel 아키텍처)로 사용하는 방법이 있다

colima라는 오픈소스 라이브러리를 설치하는 것이다.

![3](https://github.com/choiminjun94/Setting/assets/60457431/39ef052b-0ffa-4f62-8dc6-b287302aab3d)

```sql 

brew install colima

```

설치하는데 생각보다 시간이 오래 걸린다. 

![4](https://github.com/choiminjun94/Setting/assets/60457431/be5f58cf-85c8-4963-afb5-3300025e9ce8)

### colima 시작

``` sql 

colima start --arch x86_64 --cpu 4 --memory 8 

```

## Oracle 설치 

Oracle Database 11gR2 XE (11.2.0.2) 설치

![5](https://github.com/choiminjun94/Setting/assets/60457431/647ea13a-1cdd-48c0-9737-f96b59cb0192)

``` sql 

docker search oracle-xe-11g 

```


![6](https://github.com/choiminjun94/Setting/assets/60457431/bf1c1e67-02aa-4260-8cf3-f37024d913ef)


``` sql 

docker pull jaspeen/oracle-xe-11g

```

오라클 서버를 띄우는 명령어로 PASSWORD="각자 원하는 비밀번호"로 옵션을 변경

![7](https://github.com/choiminjun94/Setting/assets/60457431/43380df5-8f59-40d9-9423-762d34e66559)

``` sql 

docker run -e ORACLE_PASSWORD=비번 -p 1521:1521 -d gvenzl/oracle-xe

```

## 디비버 연결

```sql

Database : xe
UserName : system
Password : 자신이 저장한것 

Test Connection > Download > 확인

```
![스크린샷 2023-11-18 오전 1 30 00](https://github.com/choiminjun94/Setting/assets/60457431/ed9cd863-9ab8-4dbb-9253-20fb81987d70)

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
![스크린샷 2023-11-18 오전 1 31 18](https://github.com/choiminjun94/Setting/assets/60457431/0562a6ed-fab8-48d3-91cb-e04631ec0167)


## 맥 재실행 시 도커 실행 및 오라클 실행 


``` cmd 

colima start --memory 4 --arch x86_64

```

![스크린샷 2023-12-03 오후 3 52 09](https://github.com/choiminjun94/Setting/assets/60457431/4119805b-9c70-4678-9806-5f4231a22e75)


```cmd 

docker ps -a 

```

![스크린샷 2023-12-03 오후 3 52 33](https://github.com/choiminjun94/Setting/assets/60457431/4643e4f7-1fbc-48bc-bc8e-923f6af2a2bd)


```cmd

docker start CONTANER ID

ex) docker start 137221c44730

```

![스크린샷 2023-12-03 오후 3 52 47](https://github.com/choiminjun94/Setting/assets/60457431/b4de1046-2cb0-4caa-855f-841c559d2898)


```sql 

docker exec -it scott sqlplus

```

![스크린샷 2023-12-03 오후 3 53 11](https://github.com/choiminjun94/Setting/assets/60457431/946439b8-6c0f-4542-aafa-539e6d9a3bed)

```sql 

Enter user-name: system
Enter password: oracle

```

![스크린샷 2023-12-03 오후 3 53 19](https://github.com/choiminjun94/Setting/assets/60457431/6c76795e-b57c-48bc-b174-39fd2950ab3c)



 


