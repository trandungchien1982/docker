# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [02.RabbitMQ]
==============================================================

**Docker Images tạo môi trường RabbitMQ:**<br/>
(phiên bản 3.12.6 test thấy ổn định, một vài phiên bản khác lại gặp lỗi UI Management không hiện lên)

**RabbitMQ 3.12.6**
```shell
-- Init+Start RabbitMQ
docker-compose -f 01.docker-compose.3.12.6.yml up


-- Start/Stop RabbitMQ
docker-compose -f 01.docker-compose.3.12.6.yml start
docker-compose -f 01.docker-compose.3.12.6.yml stop


-- Remove all
docker-compose -f 01.docker-compose.3.12.6.yml down
```

**Truy cập vào RabbitMQ 3.12.6*
```shell
UI Management: http://localhost:15672
Usr : admin
Pwd : admin
Port: 56720
```