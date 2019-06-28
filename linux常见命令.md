
## linux 常见命令

- BASH: NETSTAT: 未找到命令
   yum -y install net-tools
- gedit 文本编辑器 对对中文有很好的支持
- 用root修改普通用户密码 passwd 用户名

## nginx 命令

 - 启动命令
    ./nginx -c /usr/local/nginx/conf/nginx.conf
    
 - 重载
    /usr/local/nginx/sbin/nginx -s  reload 
 ### windows中命令
   - 启动
      C:\server\nginx-1.0.2>nginx.exe 或 C:\server\nginx-1.0.2>start nginx
   - 停止
     C:\server\nginx-1.0.2>nginx.exe -s stop 或  C:\server\nginx-1.0.2>nginx.exe -s quit
   - 重载
     C:\server\nginx-1.0.2>nginx.exe -s reload
   - 重新打开日志文件
     C:\server\nginx-1.0.2>nginx.exe -s reopen
   - 查看Nginx版本
     C:\server\nginx-1.0.2>nginx -v 

## docker 命令

 序号|命令| 命令描述|备注
 ---|---|---|---
1| docker container port redis|查看端口映射|
2|docker container diff redis |查看变更 |
3| docker pull|下载镜像|
4|docker images|查看镜像 |
5.|docker tag 旧标签 新标签 | 更新标签|
6.| docker run -d -p 5000:5000 -v /home/ewhine/registry:/var/lib/registry registry:2 |创建私人仓库|
7|docker info |查看docker状态|
8|docker volume create -d local test | 创建数据卷| 子命令 ： inspect 查看详情、ls 列出已有数据卷 、prune 清理无用数据卷、rm 删除
9|docker run -d -P  --mount  type=bind,source=/webapp,destination=/opt/webapp training/webapp python app.py |创建数据卷|--mount 后面的参数不能有空格 type 有三种类型的参数 bind：绑定到指定路径 volume：普通数据卷，映射到主机/var/lib/docker/volumes 路径下
10|docker run -it -v /dbdata --name dbdata ubuntu:14.04|创建数据卷容器|
11|docker port 容器id |查看容器映射端口
12|docker rename 容器id 新的容器名字|修改容器名字
13|docker inspect 容器id|容器详情
14|docker ps |查看容器|子命令 -a 查看已经创建容器 -s 查看正在运行的容器
15|docker run --rm --name web2 --link mysql:mysql training/webapp env |env 查看web容器的环境变量
16|docker network ls  | 列出所有网络
17|docker network prune | 清除无用的网络
18|docker run busybox env | 查看镜像的环境变量
19|docker system prune --volumes -f | 清除无用的容器、网络、挂在卷、临时镜像、和缓存
20|








##docker 下载和安装镜像

- docker pull mysql

### 启动
- docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=Lzslov123! -d mysql

### 进入容器
- docker exec -it mysql bash

### 登录mysql
- mysql -u root -p
- ALTER USER 'root'@'localhost' IDENTIFIED BY 'Lzslov123!'; 修改 本地root用户的密码

 

### 添加远程登录用户
- CREATE USER 'liaozesong'@'%' IDENTIFIED WITH mysql_native_password BY 'Lzslov123!'; 创建用户 并且设置密码
- GRANT ALL PRIVILEGES ON *.* TO 'liaozesong'@'%'; 把权限赋给 创建的用户


##docker 安装和使用redis
###  下载和运行 redis
- docker run --name redis-container -d redis  

### docker 链接创建的 redis-container容器
- docker run -it --link redis-container:redis alpine sh 
### 进入 redis客户端
-  docker run -it --link redis-container:redis --entrypoint redis-cli redis -h redis



 

 








    
   