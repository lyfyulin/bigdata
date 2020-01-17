 

 

1.下载zookeeper

 

2.解压配置 /zookeeper/conf/

```shell
# copy
cp zoo_sample.cfg zoo.cfg
# 编辑
vi zoo.cfg
```

 编辑内容

```properties
dataDir=/usr/soft/zokeeper/zkData

dataLogDir=/usr/soft/zookeeper/zkdatalog

 

server.1=192.168.133.3:2888:3888
server.2=192.168.133.4:2888:3888
server.3=192.168.133.5:2888:3888
```



3.创建zkData文件夹

```shell
cd /usr/soft/zookeeper

mkdir zkData

mkdir zkdatalog
```

 

```shell
scp -r zookeeper hadoop-slave1:/usr/soft/zookeeper

scp -r zookeeper hadoop-slave2:/usr/soft/zookeeper
```

 

第一台机器执行

```shell
echo "1" > /usr/soft/zookeeper/zkData/myid
```

第二台执行

```shell
echo "2" > /usr/soft/zookeeper/zkData/myid
```

第二台执行

```shell
echo "3" > /usr/soft/zookeeper/zkData/myid
```

 

4.各主机分别启动 zkServer.sh start

```shell
# 启动
./zkServer.sh start
# 查看
jps
# 查看状态
./zkServer.sh status
# 进入客户端
./zkCli.sh
# 退出
quit
# 停止服务
./zkServer.sh stop
```



如果无法启动，请删除zkData中的version-2文件夹，以及zookeeper_server.pid

然后重新启动。

 

 

 

 

 

 

 

 

 

 