# Air1 News

Air1 News 是 Air1 Quick Tools 体系里的实时新闻阅读工具。它保留原项目轻量、快速的新闻聚合体验，并加入 Air1 的品牌、部署命名和产品归属。

## 功能

- 实时新闻和热点新闻聚合
- 适合快速浏览的多栏目布局
- GitHub OAuth 登录与数据同步
- 可选缓存和 Cloudflare D1 数据库支持
- PWA 安装信息
- MCP 接口支持

## 部署

### Cloudflare Pages

- 构建命令：`pnpm run build`
- 输出目录：`dist/output/public`
- 建议项目名：`air1-news`

如需使用 D1，将 `example.wrangler.toml` 复制为 `wrangler.toml`，创建 D1 数据库后配置：

```toml
binding = "AIR1_NEWS_DB"
database_name = "air1-news-db"
database_id = "your-database-id"
```

### 环境变量

以 `example.env.server` 为模板：

```env
G_CLIENT_ID=
G_CLIENT_SECRET=
JWT_SECRET=
INIT_TABLE=true
ENABLE_CACHE=true
```

GitHub OAuth 回调地址：

```text
https://your-domain.com/api/oauth/github
```

### Docker

```sh
docker compose up
```

默认容器名和本地数据卷已使用 Air1 News 命名。

## 本地开发

需要 Node.js 20 或更高版本。

```sh
corepack enable
pnpm install
pnpm dev
```

修改新闻源定义后，重新生成源数据：

```sh
pnpm presource
```

## 项目说明

Air1 News 属于 Air1 Quick Tools，目前 SEO 和 sitemap 中的公开访问地址设置为 `https://news.air1.cn/`。

## 许可证

MIT。本项目基于原 NewsNow 项目改造，原始版权声明保留在 `LICENSE` 中。
