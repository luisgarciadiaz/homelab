# 🐳 Self-Hosted Infrastructure (Homelab)

A self-managed home server running **40+ containerized services** via Docker/Portainer — a hands-on lab for real-world DevOps, automation, and disaster recovery.

This repository is a **sanitized export**: host paths, LAN IPs, and credential references are anonymized. No `.env` files, secrets, or logs are included. See `STACK_INDEX.md` for the full stack list.

## What it does
- **Container orchestration:** 40+ services deployed and managed through **Portainer** on Docker.
- **Automated backups:** Borg-based backup pipeline (`docker-backup`) with redundant storage across local and network shares; PowerShell automation for VHDX disk optimization and VM lifecycle.
- **Security:** CrowdSec, AdGuard Home, Tailscale VPN, nginx-proxy-manager with Let's Encrypt.
- **Observability:** Loki + exporters + monitoring stack.
- **CI/CD at home:** Woodpecker and Semaphore for self-hosted pipelines.
- **Daily sync:** automated jobs mirror critical data across hosts (see `stacks/backup`, `stacks/gickup`).

## Stack
`Docker` · `Portainer` · `Borg` · `PowerShell` · `Hyper-V / VHDX` · `Tailscale` · `CrowdSec`

## Layout
```
homelab-public/
├── README.md            # this file
├── STACK_INDEX.md       # list of all 40+ stacks + which compose examples are included
├── stack-registry.json  # sanitized Portainer stack registry (names + status)
└── stacks/              # anonymized docker-compose.yml examples (one per service)
    ├── backup/
    ├── vaultwarden/
    ├── nextcloud-aio/
    ├── homeassistant/
    ├── jellyfin/
    ├── tailscale/
    └── ... (40+ total)
```

## Highlights
- End-to-end ownership: from container orchestration to recovery testing.
- Reproducible automation — infrastructure as code, not click-ops.
- Runs 24/7 as a personal "production" environment.

> Maintained by Luis García Díaz — Senior C#/.NET Developer & Project Lead.
> ⚠️ Sanitized for public sharing. Do not reintroduce real secrets, IPs, or host paths.
