# 基础镜像 openjdk:8-jre-slim 代理地址；registry.cn-hangzhou.aliyuncs.com/xfg-studio/openjdk:8-jre-slim
FROM registry.cn-hangzhou.aliyuncs.com/xfg-studio/openjdk:8-jre-slim

# 作者
MAINTAINER xiaofuge

# 配置
ENV PARAMS=""

# 时区
ENV TZ=PRC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 在容器内创建目录/home/project 用于存放应用程序和相关文件
RUN mkdir -p /home/project

# 设置工作目录为/home/project，即后续的命令都在这个工作目录下执行。
WORKDIR /home/project

# 添加应用
ADD xfg-dev-tech-app/target/xfg-dev-tech-app.jar /home/project/xfg-dev-tech-app.jar

## 在镜像运行为容器后执行的命令
ENTRYPOINT ["sh","-c","java -jar $JAVA_OPTS /home/project/xfg-dev-tech-app.jar $PARAMS"]