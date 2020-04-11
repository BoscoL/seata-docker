# seata-docker

关联项目:

https://github.com/seata/seata

https://github.com/seata/seata-docker

## 本地构建(体验)
```sh
git clone https://github.com/BoscoL/seata-docker.git
cd cd seata-docker/build/
docker build -t seata-server:1.1.0.x .\github_link\ 
or
docker build -t seata-server:1.1.0.x .\gogs_link\
```

<font color=#FF0000>注：github_link 使用的是 github 网域，而 gogs_link 的是 国内网域。</font>

## seata-server:1.1.0.x
基于 seata-server v1.1.0修改：1）支持环境变量：SEATA_IP 指定为 127.0.0.1； 2）支持从配置中心中获取IP，配置属性:
```script
server.node_${SERVER_NODE}.host，如：server.node_1.host=192.168.1.x
```
<font color=#FF0000>注：${SERVER_NODE} 为 seata-server节点的ID，默认为 1.</font>
