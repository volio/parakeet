---
title: 常用 Linux 命令（持续更新）
date: 2019-12-31 19:00:00
tags: []
---

查看端口监听

```
netstat -nlp
```

查看进程

```
ps -aux
```

连接 postgresql

```
psql -h 127.0.0.1 -p 5432 -U user -d dbname
```

连接 redis

```
redis-cli -h 127.0.0.1 -p 6379 -a "password"
```

安装 Docker

```
curl -fsSL https://get.docker.com -o get-docker.sh | sh get-docker.sh
```

Kafka Console Consumer

```
kafka-console-consumer.sh --bootstrap-server kafka-server:9092 --topic topicname
```

使用 Docker 运行一个带密码的 Redis 测试容器 （开启 AOF 快照， 公网映射）

```
docker run -d --name redis -e REDIS_PASSWORD=YOURREDISPASSWORD -p 6390:6379 --restart always redis /bin/sh -c 'redis-server --appendonly yes --requirepass ${REDIS_PASSWORD}'
```

创建 Swap 分区

```
dd if=/dev/zero of=/opt/swap/swapfile bs=1024 count=6291456 //6G swap
chmod 600 /opt/swap/swapfile
mkswap /opt/swap/swapfile
swapon /opt/swap/swapfile
echo "/opt/swap/swapfile swap swap defaults 0 0">>/etc/fstab
```

PostgreSQL 批量插入存储过程

```
CREATE FUNCTION insert(count_ integer) RETURNS integer
    LANGUAGE plpgsql AS

$$
BEGIN
    WHILE count_ > 0
        LOOP
            INSERT INTO table (column) VALUES (value);
            count_ = count_ - 1;
        END LOOP ;
    RETURN count_;
END
$$
```
