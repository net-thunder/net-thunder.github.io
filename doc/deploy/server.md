# 服务端部署

## 启动服务端

```shell
# 公网ip
ip=192.222.0.152

docker run -d \
--name net-thunder-server \
--restart=always \
--network=host \
# 数据目录
-v ./data:/app/data \
# api/web端口
-e server.port=11805 \
# controllerServer公网地址
-e sdwan.httpServer.controllerAddress=${ip}:1800 \
# controllerServer tcp公网端口
-e sdwan.controllerServer.port=1800 \
# stunServer公网IP
-e sdwan.stunServer.bindHost=${ip} \
# stunServer udp公网端口
-e sdwan.stunServer.bindPort=3478 \
# relayServer udp公网端口
-e sdwan.relayServer.bindPort=2478 \
jaspercloud/net-thunder server
```

## 配置管理端

默认账号密码
root/thunder

### 创建租户
![](/resource/add-tenant.png)

### 关闭认证选项
![](/resource/tenant.png)
