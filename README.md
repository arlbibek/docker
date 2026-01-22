# Docker Multi-Service Stack

This repository contains production-ready Docker Compose setups for multiple services. All services are isolated in their own folders with persistent volumes and environment configurations for production usage.

## Services Overview

| Service                                                                         | Purpose                                                                           | Folder                                         |
| ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------- |
| [Arcane](https://github.com/getarcaneapp/arcane)                                | Docker and container management dashboard                                         | [`arcane/`](/arcane)                           |
| [GoAccess](https://github.com/allinurl/goaccess)                                | Real‑time web log analyzer and interactive viewer for Nginx/Apache logs           | [`goaccess/`](/goaccess)                       |
| [Homer](https://github.com/bastienwirtz/homer)                                  | Static dashboard homepage for organizing and accessing frequently used services   | [`homer/`](/homer)                             |
| [Metabase](https://github.com/metabase/metabase)                                | Business intelligence tool for querying, visualizing, and sharing data dashboards | [`metabase/`](/metabase)                       |
| [n8n](https://github.com/n8n-io/n8n)                                            | Workflow automation platform                                                      | [`n8n/`](/n8n)                                 |
| [Nginx Proxy Manager](https://github.com/NginxProxyManager/nginx-proxy-manager) | User‑friendly web UI for managing Nginx reverse proxies, SSL certificates         | [`nginx-proxy-manager/`](/nginx-proxy-manager) |
| [Paperless-ngx ](https://github.com/paperless-ngx/paperless-ngx)                | Document management system that scans, indexes, and archives documents with OCR   | [`paperless-ngx/`](/paperless-ngx)             |
| [Stirling PDF](https://github.com/Stirling-Tools/Stirling-PDF)                  | Locally hosted web‑based PDF manipulation tool for merge/split/convert tasks      | [`stirling-pdf/`](/stirling-pdf)               |
| [Uptime Kuma](https://github.com/louislam/uptime-kuma)                          | Monitoring tool for checking uptime and health of websites and services           | [`uptime-kuma/`](/uptime-kuma)                 |

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/arlbibek/docker.git
   cd docker
   ```

2. Run any service individually:

   ```bash
   sudo docker compose -f <service-folder>/compose.yml up -d
   ```

   or

   ```bash
   cd <service-folder>
   sudo docker compose up -d
   ```

## Notes

- Volumes: All service data is persisted using volumes for safety.
- Ports: Only expose necessary ports publicly. Use Nginx Proxy Manager or firewall rules for security.

---

Made with ❤️ by [Bibek Aryal](https://bibeka.com.np/).
