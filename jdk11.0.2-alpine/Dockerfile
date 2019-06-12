################################################################
##基于mmd0308/base-alpine:3.7构建jre镜像
##jre版本: jdk-11.0.2_linux-x64_bin.tar.gz
##Alpine版本： 3.7
################################################################
FROM mmd0308/base-alpine:3.7
MAINTAINER HengZhaoQing(mmd0308@126.com)
COPY jdk-11.0.2_linux-x64_bin.tar.gz /tmp/jdk-11.0.2_linux-x64_bin.tar.gz
RUN echo http://mirrors.ustc.edu.cn/alpine/v3.7/main > /etc/apk/repositories  \  
    && echo http://mirrors.ustc.edu.cn/alpine/v3.7/community >> /etc/apk/repositories  \
 	&& apk update && apk upgrade  \
	#****************** 安装gclib ***********************
	&& apk --no-cache add ca-certificates wget\
	&& wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub \
	&& wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.29-r0/glibc-2.29-r0.apk \
	&& apk add glibc-2.29-r0.apk \
	&& rm glibc-2.29-r0.apk \
	# 安装jdk
	&& tar -xf /tmp/jdk-11.0.2_linux-x64_bin.tar.gz -C /tmp/ \
	&& mkdir -p /usr/lib/jvm \
	&& mv /tmp/jdk-11.0.2/*  /usr/lib/jvm/ \
	&& rm -rf /tmp/* \
	&& rm -rf /var/cache/apk/*
# 设置 jre 的环境变量
ENV JAVA_HOME /usr/lib/jvm
ENV CLASSPATH .:$JAVA_HOME/lib
ENV PATH $PATH:$JAVA_HOME/bin  

