# UNM-Server V2 🎵

> 现代化音乐API服务 - 全面重构版本

基于最新技术栈重构的高性能音乐API服务，采用Monorepo架构，提供更好的开发体验、性能和可维护性。

## ✨ 主要特性

- 🚀 **极致性能**: 基于Bun运行时和Hono框架
- 🏗️ **现代架构**: TypeScript + ESM + Monorepo
- 🎯 **类型安全**: 完整的TypeScript类型定义和Zod验证
- 🔄 **智能缓存**: Redis缓存 + 分层TTL策略
- 🌐 **全栈解决方案**: Nuxt 3前端 + API后端
- 📱 **响应式设计**: 现代化UI组件和PWA支持
- 🔧 **开发友好**: 热重载、代码检查、自动格式化
- 🐳 **容器化**: Docker多阶段构建优化
- 🚀 **边缘部署**: Vercel Edge Functions + Cloudflare Workers

## 🏗️ 项目结构

```
unm-server-v2/
├── apps/
│   ├── api/                 # Bun + Hono API服务
│   └── web/                 # Nuxt 3前端应用
├── packages/
│   ├── shared/              # 共享类型和工具
│   ├── database/            # Prisma数据库配置
│   └── config/              # 共享配置
├── docker/                  # Docker配置
├── docs/                    # 文档
└── scripts/                 # 构建和部署脚本
```

## 🚀 技术栈

### 后端

- **运行时**: Bun (极致性能)
- **框架**: Hono (轻量级、高性能)
- **语言**: TypeScript (严格模式)
- **数据库**: PostgreSQL + Prisma ORM
- **缓存**: Redis + Upstash
- **验证**: Zod (运行时类型验证)

### 前端

- **框架**: Nuxt 3 (Vue 3 + SSR/SSG)
- **语言**: TypeScript
- **样式**: TailwindCSS + Nuxt UI
- **状态管理**: Pinia
- **构建工具**: Vite

### 开发工具

- **包管理**: pnpm (Monorepo)
- **代码质量**: ESLint + Prettier + TypeScript
- **测试**: Vitest + Playwright
- **CI/CD**: GitHub Actions
- **容器化**: Docker

## 🛠️ 开发环境要求

- Node.js >= 20.0.0
- pnpm >= 9.0.0
- Bun >= 1.0.0 (可选，用于API服务)

## 🚀 快速开始

### 1. 安装依赖

```bash
# 安装所有依赖
pnpm install
```

### 2. 环境配置

```bash
# 复制环境变量模板
cp .env.example .env

# 编辑环境变量
vim .env
```

### 3. 启动开发服务

```bash
# 启动所有服务（并行）
pnpm dev

# 或分别启动
pnpm --filter @unm/api dev    # API服务
pnpm --filter @unm/web dev    # 前端应用
```

### 4. 构建生产版本

```bash
# 构建所有包
pnpm build

# 启动生产服务
pnpm start
```

## 📦 包说明

### @unm/shared

共享类型定义和工具函数，包含：

- API响应类型
- 音乐相关类型定义
- 通用工具函数
- Zod验证Schema

### @unm/config

配置管理包，提供：

- 环境变量验证
- 配置加载和验证
- 类型安全的配置访问

### @unm/database

数据库相关配置：

- Prisma Schema定义
- 数据库迁移
- 类型生成

## 🔧 开发命令

```bash
# 开发
pnpm dev                    # 启动所有服务
pnpm dev:api               # 仅启动API服务
pnpm dev:web               # 仅启动前端

# 构建
pnpm build                 # 构建所有包
pnpm build:api             # 构建API服务
pnpm build:web             # 构建前端

# 测试
pnpm test                  # 运行所有测试
pnpm test:unit             # 单元测试
pnpm test:e2e              # 端到端测试

# 代码质量
pnpm lint                  # 代码检查
pnpm lint:fix              # 自动修复
pnpm format                # 代码格式化
pnpm typecheck             # 类型检查

# 数据库
pnpm db:generate           # 生成Prisma客户端
pnpm db:push               # 推送Schema到数据库
pnpm db:migrate            # 运行迁移
pnpm db:studio             # 打开Prisma Studio

# Docker
pnpm docker:build          # 构建Docker镜像
pnpm docker:run            # 运行Docker容器
```

## 🌐 API文档

API文档将在开发服务启动后自动生成，访问：

- 开发环境: http://localhost:5678/docs
- 生产环境: https://your-domain.com/docs

## 📝 环境变量

详细的环境变量配置请参考 `.env.example` 文件。

主要配置项：

- `NODE_ENV`: 运行环境
- `PORT`: API服务端口
- `DATABASE_URL`: 数据库连接字符串
- `REDIS_URL`: Redis连接字符串
- `ALLOWED_DOMAIN`: CORS允许的域名

## 🚀 部署

### Vercel部署

```bash
# 安装Vercel CLI
npm i -g vercel

# 部署
vercel --prod
```

### Docker部署

```bash
# 构建镜像
docker build -t unm-server-v2 .

# 运行容器
docker run -p 3000:3000 -p 5678:5678 unm-server-v2
```

## 🤝 贡献指南

1. Fork 项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开 Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏 致谢

- 原项目贡献者
- 开源社区的支持
- 所有使用和反馈的用户

---

**注意**: 这是UNM-Server的V2重构版本，采用了全新的技术栈和架构。如果您需要使用V1版本，请切换到相应的分支。
