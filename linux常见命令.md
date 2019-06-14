
## linux 常见命令
````
- BASH: NETSTAT: 未找到命令
   yum -y install net-tools
- gedit 文本编辑器 对对中文有很好的支持
- 用root修改普通用户密码 passed 用户名
`````
### nginx 命令
````
 - 启动命令
    ./nginx -c /usr/local/nginx/conf/nginx.conf
    
 - 重载
    /usr/local/nginx/sbin/nginx -s  reload 
 -windows 中 命令
   -- 启动
      C:\server\nginx-1.0.2>nginx.exe 或 C:\server\nginx-1.0.2>start nginx
   -- 停止
     C:\server\nginx-1.0.2>nginx.exe -s stop 或  C:\server\nginx-1.0.2>nginx.exe -s quit
   -- 重载
     C:\server\nginx-1.0.2>nginx.exe -s reload
   --重新打开日志文件
     C:\server\nginx-1.0.2>nginx.exe -s reopen
   --查看Nginx版本
     C:\server\nginx-1.0.2>nginx -v 
````
### docker 命令

 序号|命令| 命令描述
 ---|---|---
1| docker container port redis|查看端口映射
2|docker container diff redis |查看变更 
3| docker pull|下载镜像
4|docker images|查看镜像 
5.|docker tag 旧标签 新标签 | 更新标签
6.| docker run -d -p 5000:5000 -v /home/ewhine/registry:/var/lib/registry registry:2 |创建私人仓库
7|docker info |查看docker状态






    
   