# Air1 News

Air1 News is a quiet, fast real-time news reader in the Air1 Quick Tools collection. It keeps the original lightweight news aggregation workflow, then applies Air1 branding, Cloudflare-friendly deployment defaults, and a cleaner product identity.

## Features

- Real-time and trending news reading
- Clean column-based layout for quick scanning
- GitHub OAuth login and cross-device sync
- Optional cache and Cloudflare D1 database support
- PWA install metadata for a standalone app experience
- MCP endpoint support for tool-based news access

## Deployment

### Cloudflare Pages

- Build command: `pnpm run build`
- Output directory: `dist/output/public`
- Suggested project name: `air1-news`

For D1, copy `example.wrangler.toml` to `wrangler.toml`, create a Cloudflare D1 database, then set:

```toml
binding = "AIR1_NEWS_DB"
database_name = "air1-news-db"
database_id = "your-database-id"
```

### Environment Variables

Use `example.env.server` as the starting point:

```env
G_CLIENT_ID=
G_CLIENT_SECRET=
JWT_SECRET=
INIT_TABLE=true
ENABLE_CACHE=true
```

For GitHub OAuth, set the callback URL to:

```text
https://your-domain.com/api/oauth/github
```

### Docker

```sh
docker compose up
```

The default container name and local volume use the Air1 News naming.

## Development

Requires Node.js 20 or newer.

```sh
corepack enable
pnpm install
pnpm dev
```

Regenerate source metadata after changing source definitions:

```sh
pnpm presource
```

## Project Notes

Air1 News is part of Air1 Quick Tools and is maintained as a personalized fork for Air1 deployments. The public app URL is currently set to `https://news.air1.cn/` in SEO and sitemap metadata.

## License

MIT. This project is based on the original NewsNow project; original copyright notices remain in `LICENSE`.
