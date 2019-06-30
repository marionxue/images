[TOC]

# elasticsearch 7.0升级方案

## elasticsearch 7.0

1. 准备elasticsearch程序包

2. 修改配置文件以及日志存储策略

   ```bash
   # https://www.elastic.co/guide/en/elasticsearch/reference/index.html
   
   cluster.name: my-es
   node.name: cluster-node1
   node.master: true
   node.data: true
   
   # 数据存放目录，多个目录使用逗号分割
   path.data: /data/elasticsearch/data
   
   # 绑定HTTP端口
   http.port: 9200
   
   # 日志目录
   path.logs: /var/log/elasticsearch
   
   # 绑定地址，以便于外网访问
   network.host: 172.16.132.134
   
   #表示开启跨域访问支持，默认为false
   http.cors.enabled: true
   
   #表示跨域访问允许的域名地址，，可支持正则表达式，这里“*”表示允许所有域名访问
   http.cors.allow-origin: "*"
   
   #允许跨域访问头部信息
   #http.cors.allow-headers: "X-Requested-With,Content-Type, Content-Length, Authorization" 
   
   # 配置host以便于节点启动的时候更快发现其他节点，默认["127.0.0.1", "[::1]"]
   discovery.seed_hosts: ["172.16.132.135", "172.16.132.136"]
   
   # Bootstrap the cluster using an initial set of master-eligible nodes:
   #cluster.initial_master_nodes: ["node-1", "node-2","node-3"]
   
   #设置true用来锁住物理内存
   #bootstrap.memory_lock: true
   
   #索引字段缓存大小
   #indices.fielddata.cache.size: 50mb 
   
   #设置集群中master节点初始列表，可通过这些
   #discovery.zen.ping.unicast.hosts: ["192.168.37.134:9300","192.168.37.135:9300","192.168.37.136:9300"] 
   
   #配置当前集群最少的master节点数，默认为1
   #discovery.zen.minimum_master_nodes: 1
   ```

   

   

3. 配置systemd服务管理

4. 启动服务，监测服务选举是否正常

## logstash

1. 准备elasticsearch程序包
2. 修改配置文件以及日志存储策略
3. 配置systemd服务管理
4. 启动服务，监测服务选举是否正常

## filebeat

1. 准备elasticsearch程序包
2. 修改配置文件以及日志存储策略
3. 配置systemd服务管理
4. 启动服务，监测服务选举是否正常

## kibana

1. 准备elasticsearch程序包
2. 修改配置文件以及日志存储策略
3. 配置systemd服务管理
4. 启动服务，监测服务选举是否正常