# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [04.ActiveMQ]
==============================================================

**Docker Images tạo môi trường ActiveMQ 5.14.2-Alpine:**<br/>
(sử dụng phiên bản alpine cho nó lightweight)

```shell
-- Init+Start ActiveMQ
docker-compose -f 01.docker-compose.5.14.2.yml up


-- Start/Stop PostgreSQL
docker-compose -f 01.docker-compose.5.14.2.yml start
docker-compose -f 01.docker-compose.5.14.2.yml stop


-- Remove all
docker-compose -f 01.docker-compose.5.14.2.yml down
```

```shell
tdc@Mtdc % docker-compose -f 01.docker-compose.5.4.2.yml up
Pulling active-mq-custom (rmohr/activemq:5.14.2-alpine)...
5.14.2-alpine: Pulling from rmohr/activemq
e7c96db7181b: Already exists
f910a506b6cb: Pull complete
b6abafe80f63: Pull complete
414159afd29f: Pull complete
Digest: sha256:5e1166a4e165c68279e8094d7afc35d12fd6f110d9c34cf723bb5792c63a8130
Status: Downloaded newer image for rmohr/activemq:5.14.2-alpine
Creating activemq_active-mq-custom_1 ... done
Attaching to activemq_active-mq-custom_1
active-mq-custom_1  | INFO: Loading '/opt/activemq/bin/env'
active-mq-custom_1  | INFO: Using java '/usr/lib/jvm/java-1.8-openjdk/jre/bin/java'
active-mq-custom_1  | INFO: Starting in foreground, this is just for debugging purposes (stop process by pressing CTRL+C)
active-mq-custom_1  | INFO: Creating pidfile /opt/activemq/data/activemq.pid
active-mq-custom_1  | Java Runtime: IcedTea 1.8.0_212 /usr/lib/jvm/java-1.8-openjdk/jre
active-mq-custom_1  |   Heap sizes: current=62976k  free=58698k  max=932352k
active-mq-custom_1  |     JVM args: -Xms64M -Xmx1G -Djava.util.logging.config.file=logging.properties -Djava.security.auth.login.config=/opt/activemq/conf/login.config -Dcom.sun.management.jmxremote -Djava.awt.headless=true -Djava.io.tmpdir=/opt/activemq/tmp -Dactivemq.classpath=/opt/activemq/conf:/opt/activemq/../lib/: -Dactivemq.home=/opt/activemq -Dactivemq.base=/opt/activemq -Dactivemq.conf=/opt/activemq/conf -Dactivemq.data=/opt/activemq/data
active-mq-custom_1  | Extensions classpath:
active-mq-custom_1  |   [/opt/activemq/lib,/opt/activemq/lib/camel,/opt/activemq/lib/optional,/opt/activemq/lib/web,/opt/activemq/lib/extra]
active-mq-custom_1  | ACTIVEMQ_HOME: /opt/activemq
active-mq-custom_1  | ACTIVEMQ_BASE: /opt/activemq
active-mq-custom_1  | ACTIVEMQ_CONF: /opt/activemq/conf
active-mq-custom_1  | ACTIVEMQ_DATA: /opt/activemq/data
active-mq-custom_1  | Loading message broker from: xbean:activemq.xml
active-mq-custom_1  |  INFO | Refreshing org.apache.activemq.xbean.XBeanBrokerFactory$1@4883b407: startup date [Sat Nov 04 16:07:55 GMT 2023]; root of context hierarchy
active-mq-custom_1  |  INFO | Using Persistence Adapter: KahaDBPersistenceAdapter[/opt/activemq/data/kahadb]
active-mq-custom_1  |  INFO | PListStore:[/opt/activemq/data/localhost/tmp_storage] started
active-mq-custom_1  |  INFO | Apache ActiveMQ 5.14.2 (localhost, ID:1f9e499242b3-35223-1699114076505-0:1) is starting
active-mq-custom_1  |  INFO | Listening for connections at: tcp://1f9e499242b3:61616?maximumConnections=1000&wireFormat.maxFrameSize=104857600
active-mq-custom_1  |  INFO | Connector openwire started
active-mq-custom_1  |  INFO | Listening for connections at: amqp://1f9e499242b3:5672?maximumConnections=1000&wireFormat.maxFrameSize=104857600
active-mq-custom_1  |  INFO | Connector amqp started
active-mq-custom_1  |  INFO | Listening for connections at: stomp://1f9e499242b3:61613?maximumConnections=1000&wireFormat.maxFrameSize=104857600
active-mq-custom_1  |  INFO | Connector stomp started
active-mq-custom_1  |  INFO | Listening for connections at: mqtt://1f9e499242b3:1883?maximumConnections=1000&wireFormat.maxFrameSize=104857600
active-mq-custom_1  |  INFO | Connector mqtt started
active-mq-custom_1  |  WARN | ServletContext@o.e.j.s.ServletContextHandler@4278284b{/,null,STARTING} has uncovered http methods for path: /
active-mq-custom_1  |  INFO | Listening for connections at ws://1f9e499242b3:61614?maximumConnections=1000&wireFormat.maxFrameSize=104857600
active-mq-custom_1  |  INFO | Connector ws started
active-mq-custom_1  |  INFO | Apache ActiveMQ 5.14.2 (localhost, ID:1f9e499242b3-35223-1699114076505-0:1) started
active-mq-custom_1  |  INFO | For help or more information please see: http://activemq.apache.org
active-mq-custom_1  |  INFO | No Spring WebApplicationInitializer types detected on classpath
active-mq-custom_1  |  INFO | ActiveMQ WebConsole available at http://0.0.0.0:8161/
active-mq-custom_1  |  INFO | ActiveMQ Jolokia REST API available at http://0.0.0.0:8161/api/jolokia/
active-mq-custom_1  |  INFO | Initializing Spring FrameworkServlet 'dispatcher'
active-mq-custom_1  |  INFO | No Spring WebApplicationInitializer types detected on classpath
active-mq-custom_1  |  INFO | jolokia-agent: Using policy access restrictor classpath:/jolokia-access.xml
```

**Truy cập vào ActiveMQ UI**
```shell
Server: localhost
Usr : admin
Pwd : admin
```