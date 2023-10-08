# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [01.MySQL]
==============================================================

**Docker Images tạo môi trường MySQL:**<br/>

**MySQL 8.1.0**
```shell
-- Init+Start MySQL
docker-compose -f 01.docker-compose.8.1.0.yml up


-- Start/Stop MySQL
docker-compose -f 01.docker-compose.8.1.0.yml start
docker-compose -f 01.docker-compose.8.1.0.yml stop


-- Remove all
docker-compose -f 01.docker-compose.8.1.0.yml down
```

**Truy cập vào MySQL 8.1.0**
```shell
URL : localhost
Usr : root
Pwd : root
Port: 4306

```