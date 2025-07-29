# Grafana Application Monitoring Dashboard

This project provides a Grafana dashboard for monitoring various applications, with metrics and logs collected via Prometheus and Loki.

## Project Structure

- `docker-compose.yml`: Docker Compose file to set up the monitoring stack (Grafana, Prometheus, Loki, etc.).
- `prometheus.yml`: Prometheus configuration file for scraping metrics.
- `dashboards/`: Contains Grafana dashboard definitions (can be used for any app).
- `provisioning/dashboards/dashboards.yml`: Grafana provisioning config for dashboards.
- `provisioning/datasources/datasource.yml`: Grafana provisioning config for data sources.

## Usage

1. **Start the stack**:
   ```fish
   docker compose up -d
   ```
2. **Access Grafana**:
   - URL: [http://localhost:6060](http://localhost:6060)
   - Default credentials: `admin` / `admin`
3. **Import Dashboard**:
   - Dashboards in `dashboards/` are auto-provisioned.
   - If not, import them manually via the Grafana UI.

## Data Sources

- **Prometheus**: For metrics (request/response counts, rates, etc.).
- **Loki**: For logs (structured and raw).

## Customization

- Edit `prometheus.yml` to add/remove scrape targets for your apps.
- Add or edit dashboards in `dashboards/` to customize panels or queries for your use case.
- Add new panels for additional metrics as needed.

## Requirements

- Docker & Docker Compose
- Applications instrumented with Prometheus metrics and logs sent to Loki

## Troubleshooting

- Check container logs with `docker compose logs <service>`
- Ensure Prometheus and Loki are scraping/receiving data from your applications
- Verify data sources in Grafana are correctly configured

---

**Author:** Cl3tus
**License:** MIT
