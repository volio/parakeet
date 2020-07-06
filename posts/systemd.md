---
title: Systemd 配置
date: 2020-01-07 14:00:00
tags: []
---

## 自动重启配置

自动重启主要依赖三个配置参数，分别是 Restart、 StartLimitIntervalSec 和 StartLimitBurst。

### Restart

- no：不会重启
- on-success：正常退出时重启
- on-failure：非正常退出时重启
- on-abnormal：被信号终止或超时时重启
- on-watchdog
- on-abort
- always：只要退出就重启

### 频率限制

StartLimitIntervalSec 用于指定一个重启间隔，默认为 10。StartLimitBurst 指在上述重启间隔内进程最多重启的次数。

### 示例

综合以上三个参数，给出的示例配置如下：

```
StartLimitInterval=14400
StartLimitBurst=10
Restart=on-failure
```

代表 14400 秒内最多允许进程重启十次，当非正常退出时重启。
