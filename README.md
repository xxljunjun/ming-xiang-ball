## 开发

```bash
# 克隆项目
git clone https://gitlab.autel.com/base/autel-web-admin.git

# 进入项目目录
cd autel-web-admin

# 安装依赖
npm install

# 配置npm私服
npm install --registry=http://nexus.autel.com/repository/npm/

# 启动服务
npm run dev
```

重要！！！
安装 vscode eslint、prettier 插件，统一团队代码风格

```bash

# 设置git检出代码的时候不把lf转为crlf
git config --global core.autocrlf input

```

浏览器访问 http://localhost:9002

## 发布

```bash
# 构建开发环境
npm run build:dev

# 构建测试环境
npm run build:testus

# 构建生产环境
npm run build:prod
```
