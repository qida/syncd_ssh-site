---
title: 配置
date: 2017-01-05
description: >
  工具 **配置** 文件介绍。
categories: [Examples]
tags: [docs]
---

{{% pageinfo %}}

{{% /pageinfo %}}

#### 配置文件各字段含义

| 字段       | 含义                                  | 默认        | 
|-----------|---------------------------------------|-------------|
|Enable     |开关                                    |必填             |
|Name       |名称                                    |必填             |
|IP         |SSH服务地址                             |必填             |
|Port       |SSH服务端口                             |必填             |
|User       |SSH用户名                               |必填             |
|Cert       |SSH证书                                 |             |
|PassInput  |SSH密码。仅填写一次生成加密密码后自动为空。|必填             |
|PassEncrypt|由软件生成。请勿手动填写，保持为空         |             |
|Files      |支持多个文件同步                         |             |
|Dirs       |支持多个目录同步                         |             |
|SSHs       |同步完成后可执行shell命令                |             |

----------------

config.yaml文件的配置如下：

```
Hosts:
  - Enable: true                                     #开关
    Name: WSL                                        #名称
    IP: localhost                                    #SSH服务地址
    Port: 22                                         #SSH服务端口
    User: qida                                       #SSH用户名
    Cert: ""                                         #SSH证书
    PassInput: ""                                    #SSH密码。仅填写一次生成加密密码后自动为空。
    PassEncrypt: c3VucWlkYS4=                        #由软件生成。请勿手动填写，保持为空
    Files:                                           #支持多个文件同步
      - Src: D:\upgrade\label_center.tar             #源文件地址
        Dst: /mnt/d/instance/latest/label_center.tar #目标文件地址
      - Src: ""                                      #支持多个文件同步
        Dst: ""                                      #支持多个文件同步
    Dirs:                                            #支持多个目录同步
      - Src: D:\upgrade\local\                       #源目录地址
        Dst: /mnt/d/instance/latest/                 #目标目录地址
    SSHs:
      - /mnt/d/instance/update.sh v1.0.5             #同步完成后可执行shell命令
  - Enable: true                                     #开关
    Name: WSL                                        #名称
    IP: localhost                                    #SSH服务地址
    Port: 22                                         #SSH服务端口
    User: qida                                       #SSH用户名
    ...      
```
