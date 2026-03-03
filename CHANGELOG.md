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

## v1.1.0 — 2026-03-03

### Added
- `DETECT.md`: Stack fingerprinting — auto-detects WordPress, Laravel, PHP, Node.js, Next.js, NestJS, Nuxt, Python, Go, Rust
- **Phase 0 routing table** in `SKILL.md` — project type detection before any Docker work
- **5 production Dockerfiles**: Laravel (PHP 8.3-fpm), Next.js (standalone), Node.js (multi-stage), PHP generic (Apache), Python/FastAPI
- **4 compose templates**: Laravel+MySQL+Redis+Queue, Next.js+Postgres, Node.js API+Postgres, FastAPI+Postgres+Celery+Redis
- **4 native deploy guides**: WordPress (one-click + Git), Laravel (composer+artisan), PHP, Node.js
- **Decision matrix** (`references/xcloud-deploy-paths.md`): Native vs Docker by stack + DB + background jobs
- **2 new examples**: Laravel native end-to-end, Next.js Docker end-to-end
- README: SkillsMP badge, Codex CLI install instructions, full compatibility table

### Changed
- `SKILL.md` description updated to reflect full project-aware deployment capability
- README rewritten for SkillsMP/Claude Code/Codex CLI discoverability

## v1.0.0 — 2026-03-03

### Initial Release
- Scenario A: Build-from-source (generate GitHub Actions → GHCR)
- Scenario B: Proxy conflict (remove Caddy/Traefik, add nginx-router)
- Scenario C: Multi-service build (matrix GitHub Actions workflow)
- External config file embedding via Docker `configs:` block
- References: xCloud constraints, scenario deep-dives
- Examples: Rybbit Analytics, custom Dockerfile, fullstack monorepo
