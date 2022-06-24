列出所有正在运行的容器
``` powershell
docker ps

```

列出所有可用的docker镜像
``` powershell
docker images
```

获取镜像（https://hub.docker.com）
```powershell
docker pull <image>:<tag>

eg: docker pull postgres:12-alpine
```

启动一个容器
```powershell
docker run --name <container_name> -e <environment_variable> -p <host_ports:container_ports> -d <image>:<tag>

eg: docker run --name postgres12 -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=123456 -d postgres:12-alpine

// -p <host_ports:container_ports> 端口映射
// -d: 表示让docker将这个容器后台运行（分离模式）
```

在容器中运行命令
```powershell
docker exec -it <container_name_or_id> <command>[args]

eg: docker exec -it postgres12 psql -U root

// -it 以交互式会话运行
```

查看容器的日志
```powershell
docker logs <container_name_or_id>
```