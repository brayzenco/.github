# Brayzen

> The best money app for Nigerians.

Brayzen is a modern personal finance platform that helps Nigerians understand their money, track spending, manage budgets, and build savings — powered by AI.

## Architecture

```
┌─────────────────────────────────────────────────┐
│               Mobile App (Expo)                 │
│          iOS + Android (React Native)           │
└──────────────────────┬──────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────┐
│              Brayzen API (Bun)                  │
│            HonoJS · Modular Monolith            │
│                                                 │
│   finance · banking · identity · savings        │
│   intelligence · messaging · billing · system   │
└──────────┬──────────────────┬───────────────────┘
           │                  │
┌──────────▼──────┐  ┌───────▼───────────────────┐
│  PostgreSQL 17  │  │  Python ML Sidecar (gRPC) │
│  Drizzle ORM    │  │  scikit-learn · anomaly    │
│                 │  │  categorization · fraud    │
└─────────────────┘  └───────────────────────────┘
           │
┌──────────▼──────────────────────────────────────┐
│          Redis · BullMQ · Observability         │
│      Prometheus · Grafana · Sentry              │
└─────────────────────────────────────────────────┘
```

## Repos

| Repository | Description | Stack |
|------------|-------------|-------|
| [`brayzenapp`](https://github.com/brayzenco/brayzenapp) | Mobile app, landing page, web dashboard | Expo, React Native, Astro, Tailwind |
| [`brayzenapi`](https://github.com/brayzenco/brayzenapi) | Backend API with ML-powered transaction intelligence | Bun, HonoJS, PostgreSQL, Redis, Python |

## Tech Stack

**Backend:** Bun, HonoJS, PostgreSQL 17, Drizzle ORM, Redis, BullMQ, gRPC

**Mobile:** Expo SDK 56, React Native 0.85, Expo Router, React Query, Zustand, Zod

**ML Engine:** Python 3.12, scikit-learn, gRPC sidecar (categorization, anomaly detection, fraud detection)

**Infrastructure:** Caddy, Hetzner VPS, Prometheus, Grafana, Sentry

**Integrations:** Mono (banking), Anchor (transfers), Dojah (KYC), Cowrywise (savings), Groq/Nvidia (AI)

## Getting Started

### Mobile App

```sh
cd brayzenapp/apps/mobile
bun install
bun start
```

### API

```sh
cd brayzenapi
bun install
cp .env.example .env    # fill in values
bun run generate:keys
bun run push
bun run seed
bun run dev
```

API runs at `http://localhost:3000`. Docs at `/v1/docs`.

### Landing Page

```sh
cd brayzenapp/apps/landing
bun install
bun run dev
```

## Links

- [brayzenmoney.com](https://brayzenmoney.com)
- [brayzenmoney@gmail.com](mailto:brayzenmoney@gmail.com)
