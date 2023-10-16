# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [03.PostgreSQL]
==============================================================

**Docker Images tạo môi trường PostgreSQL 9.5.25:**<br/>
(sử dụng phiên bản alpine cho nó lightweight)

**PostgreSQL 9.5.25 bao gồm init SQL data, sử dụng file postgres-database-schema.sql**
```shell
-- Init+Start PostgreSQL
docker-compose -f 01.docker-compose.9.5.25.yml up


-- Start/Stop PostgreSQL
docker-compose -f 01.docker-compose.9.5.25.yml start
docker-compose -f 01.docker-compose.9.5.25.yml stop


-- Remove all
docker-compose -f 01.docker-compose.9.5.25.yml down
```

```shell
tdc@MacBook-Air-cua-Doan postgres % docker-compose -f 01.docker-compose.9.5.25.yml up
WARN[0000] Found orphan containers ([postgres-postgres_db-1]) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up. 
[+] Running 1/1
 ⠿ Container postgres-postgres-db-9.5.25-1  Created                                                                     0.1s
Attaching to postgres-postgres-db-9.5.25-1
postgres-postgres-db-9.5.25-1  | The files belonging to this database system will be owned by user "postgres".
postgres-postgres-db-9.5.25-1  | This user must also own the server process.
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | The database cluster will be initialized with locale "en_US.utf8".
postgres-postgres-db-9.5.25-1  | The default database encoding has accordingly been set to "UTF8".
postgres-postgres-db-9.5.25-1  | The default text search configuration will be set to "english".
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | Data page checksums are disabled.
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | fixing permissions on existing directory /var/lib/postgresql/data ... ok
postgres-postgres-db-9.5.25-1  | creating subdirectories ... ok
postgres-postgres-db-9.5.25-1  | selecting default max_connections ... 100
postgres-postgres-db-9.5.25-1  | selecting default shared_buffers ... 128MB
postgres-postgres-db-9.5.25-1  | selecting default timezone ... UTC
postgres-postgres-db-9.5.25-1  | selecting dynamic shared memory implementation ... posix
postgres-postgres-db-9.5.25-1  | creating configuration files ... ok
postgres-postgres-db-9.5.25-1  | creating template1 database in /var/lib/postgresql/data/base/1 ... ok
postgres-postgres-db-9.5.25-1  | initializing pg_authid ... ok
postgres-postgres-db-9.5.25-1  | setting password ... ok
postgres-postgres-db-9.5.25-1  | initializing dependencies ... ok
postgres-postgres-db-9.5.25-1  | creating system views ... ok
postgres-postgres-db-9.5.25-1  | loading system objects' descriptions ... ok
postgres-postgres-db-9.5.25-1  | creating collations ... sh: locale: not found
postgres-postgres-db-9.5.25-1  | ok
postgres-postgres-db-9.5.25-1  | No usable system locales were found.
postgres-postgres-db-9.5.25-1  | Use the option "--debug" to see details.
postgres-postgres-db-9.5.25-1  | creating conversions ... ok
postgres-postgres-db-9.5.25-1  | creating dictionaries ... ok
postgres-postgres-db-9.5.25-1  | setting privileges on built-in objects ... ok
postgres-postgres-db-9.5.25-1  | creating information schema ... ok
postgres-postgres-db-9.5.25-1  | loading PL/pgSQL server-side language ... ok
postgres-postgres-db-9.5.25-1  | vacuuming database template1 ... ok
postgres-postgres-db-9.5.25-1  | copying template1 to template0 ... ok
postgres-postgres-db-9.5.25-1  | copying template1 to postgres ... ok
postgres-postgres-db-9.5.25-1  | syncing data to disk ... ok
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | Success. You can now start the database server using:
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  |     pg_ctl -D /var/lib/postgresql/data -l logfile start
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | WARNING: enabling "trust" authentication for local connections
postgres-postgres-db-9.5.25-1  | You can change this by editing pg_hba.conf or using the option -A, or
postgres-postgres-db-9.5.25-1  | --auth-local and --auth-host, the next time you run initdb.
postgres-postgres-db-9.5.25-1  | waiting for server to start....LOG:  database system was shut down at 2023-10-16 07:36:59 UTC
postgres-postgres-db-9.5.25-1  | LOG:  MultiXact member wraparound protections are now enabled
postgres-postgres-db-9.5.25-1  | LOG:  database system is ready to accept connections
postgres-postgres-db-9.5.25-1  | LOG:  autovacuum launcher started
postgres-postgres-db-9.5.25-1  |  done
postgres-postgres-db-9.5.25-1  | server started
postgres-postgres-db-9.5.25-1  | CREATE DATABASE
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | /usr/local/bin/docker-entrypoint.sh: running /docker-entrypoint-initdb.d/database_schema.sql
postgres-postgres-db-9.5.25-1  | SET
postgres-postgres-db-9.5.25-1  | SET
postgres-postgres-db-9.5.25-1  | SET
postgres-postgres-db-9.5.25-1  | SET
postgres-postgres-db-9.5.25-1  | SET
postgres-postgres-db-9.5.25-1  | CREATE TABLE
postgres-postgres-db-9.5.25-1  | INSERT 0 12
postgres-postgres-db-9.5.25-1  | CREATE TABLE
postgres-postgres-db-9.5.25-1  | INSERT 0 6
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | waiting for server to shut down...LOG:  received fast shutdown request
postgres-postgres-db-9.5.25-1  | LOG:  aborting any active transactions
postgres-postgres-db-9.5.25-1  | LOG:  autovacuum launcher shutting down
postgres-postgres-db-9.5.25-1  | LOG:  shutting down
postgres-postgres-db-9.5.25-1  | .LOG:  database system is shut down
postgres-postgres-db-9.5.25-1  |  done
postgres-postgres-db-9.5.25-1  | server stopped
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | PostgreSQL init process complete; ready for start up.
postgres-postgres-db-9.5.25-1  | 
postgres-postgres-db-9.5.25-1  | LOG:  database system was shut down at 2023-10-16 07:37:01 UTC
postgres-postgres-db-9.5.25-1  | LOG:  MultiXact member wraparound protections are now enabled
postgres-postgres-db-9.5.25-1  | LOG:  autovacuum launcher started
postgres-postgres-db-9.5.25-1  | LOG:  database system is ready to accept connections
```

**Truy cập vào PostgreSQL 9.5.25**
```shell
Server: localhost
Usr : root
Pwd : root
DB: root
```