# Homelab

Personal homelab infrastructure and DevOps learning environment.

## Hardware

- CPU: Intel Core i3-3220
- RAM: 16 GB
- Storage: 500 GB HDD
- OS: Ubuntu Server

## Network

- LAN: 192.168.1.0/24
- Server: 192.168.1.8
- Tailscale: 100.69.75.54

## Applications

| Application | Purpose |
|---|---|
| Pi-hole | DNS / Ad blocking |
| Jellyfin | Media server |
| Gitea | Git server |
| Portainer | Docker management |
| Uptime Kuma | Service monitoring |
| Jenkins | CI/CD |

## Repository Structure

```text
docker/       Docker Compose applications
monitoring/   Prometheus/Grafana configuration
scripts/      Automation scripts
docs/         Homelab documentation
backups/      Backup-related configuration

Network Security

Services are intended to be accessible through:

Home LAN
Tailscale

Internet inbound access is blocked by UFW/router configuration.

DevOps Roadmap
 Docker
 Gitea
 Jellyfin
 Pi-hole
 Portainer
 Uptime Kuma
 Jenkins CI/CD
 Private Docker Registry
 Prometheus
 Grafana
 Ansible
 Terraform
 Secrets management
 Automated backups



