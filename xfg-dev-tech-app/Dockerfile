# 基础镜像 openjdk:8-jre-slim 代理地址；registry.cn-hangzhou.aliyuncs.com/xfg-studio/openjdk:8-jre-slim
FROM registry.cn-hangzhou.aliyuncs.com/xfg-studio/openjdk:8-jre-slim

# 作者
MAINTAINER xiaofuge

# 配置
ENV PARAMS=""

# 时区
ENV TZ=PRC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 添加应用
ADD xfg-dev-tech-app/target/xfg-dev-tech-app.jar /xfg-dev-tech-app.jar

## 在镜像运行为容器后执行的命令
ENTRYPOINT ["sh","-c","java -jar $JAVA_OPTS /xfg-dev-tech-app.jar $PARAMS"]
