# Backstage App

Internal Developer Portal built with [Backstage](https://backstage.io). Provides a unified platform for service catalog, software templates, technical documentation, and Kubernetes visibility.

## Stack

- **Backstage** — IDP framework
- **PostgreSQL** — persistent catalog storage
- **Kubernetes** — deployed on KinD (local) via manifests in [Backstage-GitOps](https://github.com/AngelosFikias0/Backstage-GitOps)

## Local Development

```bash
yarn install
yarn dev
```

## Build

```bash
yarn build:backend
docker build -t backstage-app:1.0.0 -f packages/backend/Dockerfile .
```

## Plugins

| Plugin | Purpose |
|---|---|
| Catalog | Service registry |
| Kubernetes | Live cluster visibility per entity |
| TechDocs | Integrated documentation |
| Scaffolder | Software templates |

## Deployment

Deployment manifests and cluster config live in the GitOps repo. See [Backstage-GitOps](https://github.com/AngelosFikias0/Backstage-GitOps).

## Structure

```
backstage-app/
├── packages/
│   ├── app/        # Frontend
│   └── backend/    # Backend + Dockerfile
├── plugins/        # Custom plugins
├── catalog/        # Catalog entities
├── app-config.yaml # Base configuration
└── examples/       # Example catalog entities
```
