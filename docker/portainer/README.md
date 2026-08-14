# Portainer

Portainer CE manages the Docker environment on the homelab server.

## Access

LAN:

https://192.168.1.8:9443

Tailscale:

https://100.69.75.54:9443

## Storage

Portainer configuration is stored in the Docker volume:

`portainer_data`

## Docker Socket

Portainer requires access to:

`/var/run/docker.sock`
