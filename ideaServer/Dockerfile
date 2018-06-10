
################################################################
##基于mmd0308/base-alpine:3.7构建ideaL IntelliJ IDEA License Server 
## 端口1027
################################################################
FROM mmd0308/base-alpine:3.7
MAINTAINER HengZhaoQing(mmd0308@126.com)
ADD ideaServer  /
RUN  chmod 777 /ideaServer
EXPOSE 1027
CMD [ "/ideaServer" ]