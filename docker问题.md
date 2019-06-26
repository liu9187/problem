# docker 问题解决
````
1.安装docker的时候出现Job for docker.service failed because the control process exited with error code. See "systemctl status docker.service" and "journalctl -xe" for details.
解决方法：vi /etc/sysconfig/selinux    把selinux后面的改为disabled，重启一波机器，再重启docker就可以了  