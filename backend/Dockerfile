# 使用官方 Node.js运行时作为父镜像
FROM node:18-alpine

# 在容器中设置工作目录
WORKDIR /usr/src/app

# 安装 pnpm
RUN npm install -g pnpm

# 复制 package.json 和 pnpm-lock.yaml
COPY package.json pnpm-lock.yaml ./

# 安装应用依赖
# 使用 --frozen-lockfile 确保使用锁定的依赖版本
RUN pnpm install --frozen-lockfile

# 将应用源代码复制到工作目录
COPY . .

# 应用监听的端口
EXPOSE 3000

# 设置环境变量，可根据需要修改
ENV NODE_ENV production
# ENV PORT 3000 # 如果应用内部需要 PORT 环境变量

# 运行应用的命令
CMD [ "pnpm", "start" ] 