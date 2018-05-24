################################################################
##基于mmd0308/centos:7.3.1611构建jre镜像
##jre版本: jre-8u171-linux-x64.tar.gz
##centos版本： 7.3.1611
################################################################
FROM mmd0308/centos:7.3.1611

MAINTAINER HengZhaoQing(mmd0308@126.com)

COPY jre-8u171-linux-x64.tar.gz /tmp/jre-8u171-linux-x64.tar.gz

RUN tar -xf /tmp/jre-8u171-linux-x64.tar.gz -C /tmp/ \
	&& mkdir -p /usr/lib/jvm \
	&& mv /tmp/jre1.8.0_171/*  /usr/lib/jvm/ \
	&& rm -rf /tmp/*

# 设置 jre 的环境变量
ENV JAVA_HOME /usr/lib/jvm
ENV CLASSPATH .:$JAVA_HOME/lib
ENV PATH $PATH:$JAVA_HOME/bin  

