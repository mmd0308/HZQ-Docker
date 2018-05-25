######################################################
## alpine 3.7 基础上构建自己的基础alpine镜像
## 已经安装软件 curl bash tzdata 设置系统时间 
## 设置时间区 Asia/Shanghai
######################################################
# 继承官方基础镜像
FROM alpine:3.7
# 作者基本信息
MAINTAINER HengZhaoQing(mmd0308@126.com)
# 清除yum 缓存 安装软件  设置时间区
# Install base packages
RUN apk update && apk add curl bash  tzdata \
    && /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime 
CMD ["/bin/bash"]