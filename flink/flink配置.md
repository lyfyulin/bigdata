

安装软件

yum install lrzsz

yum install nc



下载解压



文件配置

vi  flink/conf/flink-conf.yaml

```properties
jobmanager.rpc.address: hadoop-master
```

vi flink/conf/slaves

```properties
hadoop-slave1
hadoop-slave2
```



启动 flink 集群

```shell
# 开启 flink 集群
start-cluster.sh
```



启动后可以使用 jps 指令查看状态。

















