# docker 问题解决
````
1.安装docker的时候出现Job for docker.service failed because the control process exited with error code. See "systemctl status docker.service" and "journalctl -xe" for details.
解决方法：vi /etc/sysconfig/selinux    把selinux后面的改为disabled，重启一波机器，再重启docker就可以了  
2.本地镜像都放在那里
解决方案：与docker相关的本地资源（包括镜像、容器）默认都放在 /var/lib/docker 目录下。以aufs文件系统为例，其中container
          目录存放在容器信息，graph目录存放在镜像信息，aufs目录下存放具体的镜像文件
3.构建docker镜像应该遵循哪些原则？
解决方案： 尽量选取满足要求但是较小的基础镜像，例如：debian:wheezy 或者 debian:jessie镜像
4.