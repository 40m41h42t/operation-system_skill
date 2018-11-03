docker images 显示所有镜像 e.g

```bash
➜  ~ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
coolq/wine-coolq    latest              0b2906f2e6bf        4 months ago        1.37 GB
```

删除镜像：

停止容器后，根据IMAGE ID删除

```
docker rmi 0b2906f2e6bf
```

