######################################################
##基于Centos7.3.1611构建基础的包含常用软件的centos镜像
## 已经安装软件 vi tar wget curl ssh 
## 设置时间区 Asia/Shanghai
######################################################
# 继承官方基础镜像
FROM centos:7.3.1611
# 作者基本信息
MAINTAINER HengZhaoQing(mmd0308@126.com)
# 清除yum 缓存 安装软件  设置时间区
RUN yum clean all \
	&& yum install -y tar wget openssh-server openssh-clients \
	&& yum clean all \
	&& ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key \
	&& ssh-keygen -t dsa -f /etc/ssh/ssh_host_dsa_key \
	&& ssh-keygen -t rsa -f /root/.ssh/id_rsa \
	&& cp /root/.ssh/id_rsa.pub /root/.ssh/authorized_keys \
	&& /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
	&& echo 'Asia/Shanghai' > /etc/timezon


