## [1.1.0] - 2026-03-03

### Added
- **Phase 0: Project Detection** (`DETECT.md`) — stack fingerprinting before any deployment step
  - Auto-detects WordPress, Laravel, PHP, Next.js, NestJS, Nuxt, Node.js, Python, Go, Rust
  - Routes to native deploy path or Docker path automatically
- **Native Deploy Guides** (4 new reference files):
  - `references/xcloud-native-wordpress.md` — one-click + Git deploy, wp-config env pattern
  - `references/xcloud-native-laravel.md` — composer hooks, queue workers, scheduler
  - `references/xcloud-native-nodejs.md` — PORT env, Node 18/20/22, TypeScript builds
  - `references/xcloud-native-php.md` — web root config, Composer hooks, PHP version
- **Deployment Decision Guide** (`references/xcloud-deploy-paths.md`) — Native vs Docker matrix
- **Production Dockerfile Templates** (5 files in `dockerfiles/`):
  - `laravel.Dockerfile` — PHP 8.3-fpm-alpine, multi-stage, opcache + redis
  - `nextjs.Dockerfile` — 3-stage standalone build, non-root user
  - `node-app.Dockerfile` — Node 20-alpine, multi-stage, non-root user
  - `php-generic.Dockerfile` — PHP 8.3-apache, mod_rewrite, pdo_mysql
  - `python-fastapi.Dockerfile` — Python 3.12-slim, uvicorn, non-root user
- **Pre-configured Compose Templates** (4 files in `compose-templates/`):
  - `laravel-mysql.yml` — PHP-FPM + nginx + MySQL 8 + Redis + queue worker
  - `nextjs-postgres.yml` — Next.js + PostgreSQL 16
  - `nodejs-api-postgres.yml` — Node API + PostgreSQL 16
  - `python-fastapi-postgres.yml` — FastAPI + PostgreSQL + Redis + Celery worker
- **New Examples**:
  - `examples/laravel-app.md` — fresh Laravel → xCloud Native end-to-end
  - `examples/nextjs-app.md` — Next.js → xCloud Docker end-to-end

### Changed
- `SKILL.md` — added Phase 0 routing table before Scenario detection; updated description


# Changelog

## [1.0.0] - 2026-03-03

### Added
- Initial release
- **Scenario A** — Build-from-source: GitHub Actions + GHCR workflow generation
- **Scenario B** — Proxy conflict: removes Caddy/Traefik/nginx-proxy, adds nginx-router with inline config
- **Scenario C** — Multi-service build: matrix GitHub Actions workflow for parallel image builds
- `references/xcloud-constraints.md` — full xCloud rules and architecture
- `references/scenario-build-source.md` — Scenario A deep-dive
- `references/scenario-proxy-conflict.md` — Scenario B deep-dive
- `references/scenario-multi-service-build.md` — Scenario C deep-dive (new)
- `examples/rybbit-analytics.md` — real-world Caddy + multi-port example
- `examples/custom-app-dockerfile.md` — real-world build-from-source example
- `examples/fullstack-monorepo.md` — real-world multi-service build example
- `assets/github-actions-build.yml` — reusable GitHub Actions template
- ClawHub + SkillsMP compatible packaging
- Works with OpenClaw, Claude Code, Claude.ai Projects, Cursor, Windsurf, any AI agent
