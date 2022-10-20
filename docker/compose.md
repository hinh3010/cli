# docker-compose.yml

- mysql
  
```sql
CREATE DATABASE IF NOT EXISTS xh_db;
```

``` js

version: "3.1" 
services:
    xh_db:
        image: mysql:5.7
        volumes:
            - ./mysql/init.sql:/docker-entrypoint-initdb.d/init.sql
        // đọc file init.sql  trong folder mysql và copy vào /docker-entrypoint-initdb.d/init.sql

        command: --init-file /docker-entrypoint-initdb.d/init.sql
        // lệnh chạy khởi tạo với những gì bên trong /docker-entrypoint-initdb.d/init.sql

        ports:
            - "3312:3306"
        environment:
            MYSQL_DATABASE: xh_db
            MYSQL_ROOT_USER: uxh
            MYSQL_USER: uxh
            MYSQL_ROOT_PASSWORD: hellocacbantre
            MYSQL_PASSWORD: hellocacbantre

```

* run 
`docker-compose up`

* docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED          STATUS          PORTS                               NAMES
0bc67bf1a9c5   mysql:8.0   "docker-entrypoint.s…"   35 minutes ago   Up 35 minutes   33060/tcp, 0.0.0.0:3312->3306/tcp   node_ts_docker-xh_db-1

