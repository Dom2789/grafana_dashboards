# Homelab Grafana Dashboards

Grafana-Dashboards (JSON) für Homelab-Metriken aus **InfluxDB v2** (Bucket `telemetry`).

## Dashboards
| Datei | Inhalt |
|-------|--------|
| `proxmox-cpu-dashboard.json` | Proxmox: CPU/IO-Wait/Load/RAM für Nodes, VMs, LXC |
| `raspberry-pi-dashboard.json` | Raspberry Pis (Glances): CPU/Last/RAM/Temp, Host wählbar |
| `warmwasser-dashboard.json` | Warmwassertemperatur (24 h–90 Tage) |

## Import
Grafana → **Dashboards → New → Import → Upload JSON** → InfluxDB-Datasource wählen.
Variablen oben im Dashboard: Datasource, Bucket (`telemetry`), ggf. Host/Node.

## Datenquellen
- **Proxmox:** nativer Metric Server → `cpustat`/`system`/`memory`
- **Raspberry Pis:** Glances → `cpu`/`mem`/`load`/`sensors`
- **Warmwasser:** Measurement `environment`, Field `watertemperature`

## Zugangsdaten
InfluxDB-URL/Org/Token liegen in `influx.env` (**gitignored – nicht committen**).
