################################################################
##基于mmd0308/centos:7.3.1611构建jre镜像
##jre版本: jdk-11.0.2_linux-x64_bin.tar.gz
##centos版本： 7.3.1611
################################################################
FROM mmd0308/centos:7.3.1611

MAINTAINER HengZhaoQing(mmd0308@126.com)

COPY jdk-11.0.2_linux-x64_bin.tar.gz /tmp/jdk-11.0.2_linux-x64_bin.tar.gz

RUN tar -xf /tmp/jdk-11.0.2_linux-x64_bin.tar.gz -C /tmp/ \
	&& mkdir -p /usr/lib/jvm \
	&& mv /tmp/jdk-11.0.2/*  /usr/lib/jvm/ \
	&& rm -rf /tmp/*

# 设置 jre 的环境变量
ENV JAVA_HOME /usr/lib/jvm
ENV CLASSPATH .:$JAVA_HOME/lib
ENV PATH $PATH:$JAVA_HOME/bin  

