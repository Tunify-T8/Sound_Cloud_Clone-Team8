# Monitoring Stack

This repo now includes a minimal Dockerized monitoring overlay for:

- CPU usage
- memory usage
- disk usage for `/`
- Grafana alert rules for CPU > 95%
- Grafana alert rules for memory > 95%

## Files

- `docker-compose.monitoring.yml`
- `monitoring/prometheus/prometheus.yml`
- `monitoring/grafana/provisioning/...`
- `monitoring/grafana/dashboards/host-overview.json`

## Start it with production

```bash
docker compose -f docker-compose.prod.yml -f docker-compose.monitoring.yml up -d
```

## Start it with local dev

```bash
docker compose -f docker-compose.yml -f docker-compose.monitoring.yml up -d
```

## Access Grafana

Grafana is proxied through Caddy at:

```text
https://<your-domain>/grafana/
```

Default credentials come from environment variables:

- `GRAFANA_ADMIN_USER` default: `admin`
- `GRAFANA_ADMIN_PASSWORD` default: `change-me`

## Backend changes

No backend code changes are required for CPU, memory, or disk monitoring.

If you later want application-level metrics such as:

- request rate
- request latency
- error rate
- event loop lag
- websocket connection counts

then the backend should expose a `/metrics` endpoint with Prometheus-formatted metrics.
The Prometheus config already includes a commented scrape job for that future step.

## Notes

- `node-exporter` is collecting host metrics. On Linux servers this reports the real host.
- On Docker Desktop for macOS/Windows, it reports the Docker VM rather than the full physical host OS.
- Prometheus is intentionally not exposed publicly. Grafana talks to it over the Docker network.
- Grafana is also internal-only now and is accessed through Caddy at `/grafana/`.
