# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [06.KafkaCluster3Brokers]
==============================================================

**Tham khảo**
- https://www.baeldung.com/ops/kafka-docker-setup
- https://howtodoinjava.com/kafka/kafka-cluster-setup-using-docker-compose/
- https://github.com/conduktor/kafka-stack-docker-compose
- https://www.conduktor.io/get-started/


**Docker Images tạo môi trường Kafka Cluster dựng sẵn gồm 3 Broker:**<br/>
- ..............

**Các lệnh thực hiện**
```shell
-- Init+Start Kafka
docker-compose -f aaa.yml up


-- Start/Stop Kafka
docker-compose -f aaa.yml start
docker-compose -f aaa.yml stop


-- Remove all
docker-compose -f aaa.yml down
```

**Kết quả thực thi**
```shell
tdc@tdc:~/docker/kafka$ docker-compose -f aaa.yml up

```

**Truy cập vào Kafka UI Dashboard**
```shell
http://localhost:3030
```
