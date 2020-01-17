 

1.下载kafka安装包

 

2.解压并配置文件 kafka/config/server.properties

 有四个配置内容需要改，其中broker.id在不同的主机上不同。

```properties
broker.id=0      #每台机器不一样

delete.topic.enable=true

log.dirs=/usr/soft/kafka/logs

zookeeper.connect=hadoop-master:2181,hadoop-slave1:2181,hadoop-slave2:2181
```

 复制到 slave 机

```shell
scp -r kafka hadoop-slave1:/usr/soft/kafka

scp -r kafka hadoop-slave2:/usr/soft/kafka
```

 

```shell
# hadoop-slave1 上
vi /usr/soft/kafka/config/server.properties

# hadoop-slave2 上
vi /usr/soft/kafka/config/server.properties
```

 

 

3.确保每台zookeeper启动，查看zookeeper启动状态

```shell
# 启动每天机器 zkServer
./zkServer.sh start
# 查看 zkServer 状态
./zkServer.sh status
```

 

4.启动各台主机的kafka

```shell
# 启动 kafka
kafka-server-start.sh /usr/soft/kafka/config/server.properties
```

 

 