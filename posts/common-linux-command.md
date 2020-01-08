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
