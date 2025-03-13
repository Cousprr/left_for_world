# docker 常用指令

查看所有容器containers信息

```bash
docker ps -a
```

查看镜像images信息

```bash
docker images
```

查看容器端口信息
```bash
docker port container_name_or_id
```

复制本地文件到docker

```bash
docker cp example_file container_name_or_id:/location
```

打开docker容器命令行

```bash
docker exec -it container_name_or_id /bin/bash
```

退出

```
$ exit
```

解压tar.gz

```
$ tar -xzvf example_file.tar.gz
```
