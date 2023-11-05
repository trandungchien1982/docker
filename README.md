# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [05.KafkaSimple1Broker]
==============================================================

**Tham khảo**
- https://hub.docker.com/r/landoop/fast-data-dev


**Docker Images tạo môi trường Kafka dựng sẵn gồm 1 Broker với các UI/Tools đi kèm:**<br/>
- Apache Kafka
- Kafka Connect
- Zookeeper
- Confluent Schema Registry
- REST Proxy
- Lenses.io Lenses hoặc kafka-topics-ui, schema-registry-ui, kafka-connect-ui
- Lenses.io Stream Reactor
- 25+ Kafka Connectors để simplify ETL processes
- Integration testing và examples embedded <br/>
*(File Docker Image khá nặng và chiếm khoảng 680.53 MB)*

**Các lệnh thực hiện**
```shell
-- Init+Start Kafka
docker-compose -f 01.docker-compose.AIO.fast-data-dev.yml up


-- Start/Stop Kafka
docker-compose -f 01.docker-compose.AIO.fast-data-dev.yml start
docker-compose -f 01.docker-compose.AIO.fast-data-dev.yml stop


-- Remove all
docker-compose -f 01.docker-compose.AIO.fast-data-dev.yml down
```

**Kết quả thực thi**
```shell
tdc@tdc:~/docker/kafka$ docker-compose -f 01.docker-compose.AIO.fast-data-dev.yml up
Creating kafka_fast-dev-kafka_1 ... done
Attaching to kafka_fast-dev-kafka_1
fast-dev-kafka_1  | Starting services.
fast-dev-kafka_1  | This is Lenses.io’s fast-data-dev. Kafka 2.6.2-L0 (Lenses.io's Kafka Distribution).
fast-dev-kafka_1  | You may visit http://127.0.0.1:3030 in about a minute.
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/01-zookeeper.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/02-broker.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/03-schema-registry.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/04-rest-proxy.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/05-connect-distributed.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/06-caddy.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/07-smoke-tests.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/08-logs-to-kafka.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Included extra file "/etc/supervisord.d/99-supervisord-running-sample-data.conf" during parsing
fast-dev-kafka_1  | 2023-11-05 16:22:07,299 INFO Set uid to user 0 succeeded
fast-dev-kafka_1  | 2023-11-05 16:22:07,302 INFO RPC interface 'supervisor' initialized
fast-dev-kafka_1  | 2023-11-05 16:22:07,302 CRIT Server 'unix_http_server' running without any HTTP authentication checking
fast-dev-kafka_1  | 2023-11-05 16:22:07,303 INFO supervisord started with pid 7
fast-dev-kafka_1  | 2023-11-05 16:22:08,306 INFO spawned: 'broker' with pid 176
fast-dev-kafka_1  | 2023-11-05 16:22:08,311 INFO spawned: 'caddy' with pid 177
fast-dev-kafka_1  | 2023-11-05 16:22:08,317 INFO spawned: 'connect-distributed' with pid 178
fast-dev-kafka_1  | 2023-11-05 16:22:08,325 INFO spawned: 'logs-to-kafka' with pid 179
fast-dev-kafka_1  | 2023-11-05 16:22:08,332 INFO spawned: 'rest-proxy' with pid 185
fast-dev-kafka_1  | 2023-11-05 16:22:08,338 INFO spawned: 'running-sample-data-ais' with pid 187
fast-dev-kafka_1  | 2023-11-05 16:22:08,343 INFO spawned: 'running-sample-data-backblaze-smart' with pid 192
fast-dev-kafka_1  | 2023-11-05 16:22:08,347 INFO spawned: 'running-sample-data-taxis' with pid 196
fast-dev-kafka_1  | 2023-11-05 16:22:08,351 INFO spawned: 'running-sample-data-telecom-italia' with pid 198
fast-dev-kafka_1  | 2023-11-05 16:22:08,354 INFO spawned: 'schema-registry' with pid 201
fast-dev-kafka_1  | 2023-11-05 16:22:08,356 INFO spawned: 'smoke-tests' with pid 202
fast-dev-kafka_1  | 2023-11-05 16:22:08,359 INFO spawned: 'zookeeper' with pid 205
fast-dev-kafka_1  | 2023-11-05 16:22:09,312 INFO success: broker entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,313 INFO success: caddy entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,313 INFO success: connect-distributed entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,318 INFO success: logs-to-kafka entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,337 INFO success: rest-proxy entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,337 INFO success: running-sample-data-ais entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,341 INFO success: running-sample-data-backblaze-smart entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,352 INFO success: running-sample-data-taxis entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,353 INFO success: running-sample-data-telecom-italia entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,353 INFO success: schema-registry entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,354 INFO success: smoke-tests entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:22:09,356 INFO success: zookeeper entered RUNNING state, process has stayed up for > than 1 seconds (startsecs)
fast-dev-kafka_1  | 2023-11-05 16:23:23,901 INFO exited: logs-to-kafka (exit status 0; expected)
fast-dev-kafka_1  | 2023-11-05 16:26:03,769 INFO exited: smoke-tests (exit status 1; not expected)
```

**Truy cập vào Kafka UI Dashboard**
```shell
http://localhost:3030
```
