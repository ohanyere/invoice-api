# Runbook

## Service

- Name: `invoice-api`
- Team: `Commerce`
- Owner: `mooref068@gmail.com`
- Cost center: `commerce`

## First Checks

```bash
kubectl get rollout invoice-api -n invoice-api-dev
kubectl get pods -l app.kubernetes.io/name=invoice-api -n invoice-api-dev
kubectl logs -l app.kubernetes.io/name=invoice-api -n invoice-api-dev
```

## Health

```bash
curl https://invoice-api.dev.platform.ohanyere.internal/healthz
curl https://invoice-api.dev.platform.ohanyere.internal/readyz
curl https://invoice-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo invoice-api -n invoice-api-dev
```

Escalate to `Commerce` through `mooref068@gmail.com` if rollback does not restore service.
