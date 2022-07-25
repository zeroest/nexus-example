
# Nexus example

1. Nexus 설치 by Docker

```bash
mkdir nexus-data

docker run --name nexus -d -p 5000:5000 -p 8081:8081 -v `pwd`/nexus-data:/nexus-data -u root sonatype/nexus3
```

2. Nexus 로그인

- admin 계정 비번 찾기

```bash
-- 도커 내부 파일 확인
docker exec -it nexus cat /nexus-data/admin.password
-- 아니면 로컬에 마운트된 폴더에서 확인
cat nexus-data
```

- Nexus 웹 접속 및 로그인

```
http://localhost:8081

ID: admin
PW: `docker exec -it nexus cat /nexus-data/admin.password`
```


