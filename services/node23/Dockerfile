# Dockerfile
ARG NODE_VERSION
FROM ${NODE_VERSION}

# 设置npm镜像源
RUN npm config set registry https://registry.npmmirror.com

# 安装 pnpm 并设置淘宝镜像源
RUN npm install -g pnpm && \
    pnpm config set registry https://registry.npmmirror.com

# # 安装 yarn 并设置淘宝镜像源
# RUN npm install --global yarn && \
#     yarn config set registry https://registry.npmmirror.com


# 安装 Git
RUN apk --no-cache add git
# 安装 bash
RUN apk --no-cache add bash

# 安装 z 命令
RUN apk --no-cache add wget \
    && wget -qO /usr/local/bin/z.sh https://raw.gitmirror.com/rupa/z/master/z.sh \
    && chmod +x /usr/local/bin/z.sh \
    && echo ". /usr/local/bin/z.sh" >> /etc/profile

RUN echo ". /etc/profile" > ~/.bashrc

# 设置工作目录
WORKDIR /www