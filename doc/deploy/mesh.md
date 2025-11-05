# Mesh网关部署

## 启动mesh端
```shell
# 公网ip
ip=192.222.0.152

docker run -d \
--privileged \
--name net-thunder-mesh \
--restart=always \
# 自定义唯一的mac地址
--mac-address 42:ac:bd:00:00:00 \
# 指定租户编码
-e tenantId=default \
# controllerServer公网地址
-e controllerServer=${ip}:1800 \
-e netMesh=true \
-e showVRouterLog=true \
-e showICELog=true \
-e showElectionLog=true \
-e showRouteRuleLog=true \
jaspercloud/net-thunder mesh
```

### 查看节点管理端
![](/resource/click-node.png)

### 网关部署成功，网关节点上线
![](/resource/node-manage.png)