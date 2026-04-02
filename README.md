# OpenClaw Install Guide

[![Powered by MyClaw.ai](https://img.shields.io/badge/Powered%20by-MyClaw.ai-blue?style=for-the-badge)](https://myclaw.ai)

The definitive guide to deploying OpenClaw on any server. From one-click cloud hosting to bare-metal self-hosting.

**🌐 Language / 语言:**
[English](README.md) | [中文](README.zh-CN.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [日本語](README.ja.md) | [Italiano](README.it.md) | [Español](README.es.md)

---

## ⚡ Option 1: MyClaw.ai — One-Click Deploy (Recommended)

**The fastest way to get OpenClaw running. Zero server setup. Zero maintenance.**

[MyClaw.ai](https://myclaw.ai) gives you a fully managed OpenClaw instance — your own server with full code control, networking, and tool access. No SSH, no Docker, no config files.

[![MyClaw.ai Homepage](assets/myclaw-homepage.png)](https://myclaw.ai)

### Why MyClaw.ai?

- **One click** — Sign up, pick a plan, your instance is live in under 60 seconds
- **Full server** — Each instance is a real server running OpenClaw, not a sandboxed chatbot
- **Full code control** — Your Agent can read/write files, run shell commands, access the internet
- **Auto-updates** — Always on the latest OpenClaw version, zero downtime
- **Built-in channels** — Telegram, Discord, WhatsApp, and more — connect in seconds
- **Managed infrastructure** — Backups, monitoring, scaling handled for you
- **Skills marketplace** — Install community skills from [ClawHub](https://clawhub.ai) with one command

### Pricing

| Plan | Monthly | Annual (per month) |
|------|---------|-------------------|
| Lite | $19/mo | $16/mo ($199/yr) |
| Pro | $39/mo | $33/mo ($399/yr) |
| Max | $79/mo | $66/mo ($799/yr) |

👉 **[Get started at MyClaw.ai →](https://myclaw.ai)**

---

## 🛠️ Option 2: Self-Host OpenClaw

For developers who want full control over their infrastructure. Pick your platform:

### Quick Install (Any Linux/macOS/Windows)

```bash
# macOS / Linux / WSL2
curl -fsSL https://openclaw.ai/install.sh | bash

# Windows (PowerShell)
iwr -useb https://openclaw.ai/install.ps1 | iex
```

The installer detects your OS, installs Node.js if needed, installs OpenClaw, and launches onboarding.

### System Requirements

- **Node.js 24** (recommended) or Node 22.14+
- **OS:** macOS, Linux, or Windows (native or WSL2)
- **RAM:** 1 GB minimum (2 GB+ recommended)

---

## ☁️ Cloud VPS Deployment

### Hetzner (~$5/mo)

The cheapest reliable option for 24/7 hosting.

```bash
ssh root@YOUR_VPS_IP

# Install Docker
apt-get update && apt-get install -y git curl ca-certificates
curl -fsSL https://get.docker.com | sh

# Clone and setup
git clone https://github.com/openclaw/openclaw.git
cd openclaw
./scripts/docker/setup.sh
```

Access via SSH tunnel:
```bash
ssh -N -L 18789:127.0.0.1:18789 root@YOUR_VPS_IP
# Open http://127.0.0.1:18789
```

### DigitalOcean ($6/mo)

```bash
ssh root@YOUR_DROPLET_IP

apt update && apt upgrade -y
curl -fsSL https://deb.nodesource.com/setup_24.x | bash -
apt install -y nodejs

curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

### Oracle Cloud (Free!)

Oracle's Always Free ARM tier: up to 4 OCPU, 24 GB RAM, 200 GB storage — at zero cost.

```bash
ssh ubuntu@YOUR_PUBLIC_IP

sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential

curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon

# Recommended: Tailscale for secure remote access
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up --ssh --hostname=openclaw
openclaw config set gateway.tailscale.mode serve
```

### Fly.io (~$10-15/mo)

Managed containers with automatic HTTPS.

```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw

fly apps create my-openclaw
fly volumes create openclaw_data --size 1 --region iad
fly secrets set OPENCLAW_GATEWAY_TOKEN=$(openssl rand -hex 32)
fly secrets set ANTHROPIC_API_KEY=sk-ant-...
fly deploy
```

### Other Platforms

| Platform | Guide | Cost |
|----------|-------|------|
| [GCP](https://docs.openclaw.ai/install/gcp) | Google Cloud | Free tier available |
| [Azure](https://docs.openclaw.ai/install/azure) | Microsoft Azure | Free tier available |
| [Railway](https://docs.openclaw.ai/install/railway) | Railway | Usage-based |
| [Render](https://docs.openclaw.ai/install/render) | Render | Free tier available |
| [Northflank](https://docs.openclaw.ai/install/northflank) | Northflank | Free tier available |

---

## 🐳 Docker Deployment

For containerized or headless deployments.

```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw

# Automated setup (recommended)
./scripts/docker/setup.sh

# Or use pre-built image
export OPENCLAW_IMAGE="ghcr.io/openclaw/openclaw:latest"
./scripts/docker/setup.sh
```

### Docker Compose (Manual)

```yaml
services:
  openclaw-gateway:
    image: ghcr.io/openclaw/openclaw:latest
    restart: unless-stopped
    environment:
      - NODE_ENV=production
      - OPENCLAW_GATEWAY_TOKEN=your-secret-token
      - OPENCLAW_GATEWAY_BIND=lan
    volumes:
      - ./config:/home/node/.openclaw
      - ./workspace:/home/node/.openclaw/workspace
    ports:
      - "127.0.0.1:18789:18789"
    command: ["node", "dist/index.js", "gateway", "--bind", "lan", "--port", "18789"]
```

```bash
docker compose up -d
```

---

## 🍓 Raspberry Pi

Always-on personal AI for ~$50 hardware cost.

**Requirements:** Raspberry Pi 4/5, 2 GB+ RAM, 64-bit Raspberry Pi OS

```bash
# Flash Raspberry Pi OS Lite (64-bit), then SSH in
ssh user@gateway-host

sudo apt update && sudo apt upgrade -y
sudo apt install -y git curl build-essential

# Install Node.js 24
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
sudo apt install -y nodejs

# Add swap (important for 2GB models)
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile && sudo mkswap /swapfile && sudo swapon /swapfile
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab

# Install OpenClaw
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

**Tips:**
- Use a USB SSD instead of SD card for better performance
- Use API-based models (Claude, GPT) — don't run local models on Pi
- Disable GPU memory: `echo 'gpu_mem=16' | sudo tee -a /boot/config.txt`

---

## 🔧 Post-Install

### Verify Installation

```bash
openclaw --version
openclaw doctor
openclaw gateway status
```

### Connect Channels

```bash
# Telegram
openclaw channels add --channel telegram --token "YOUR_BOT_TOKEN"

# Discord
openclaw channels add --channel discord --token "YOUR_BOT_TOKEN"

# WhatsApp (QR code)
openclaw channels login
```

### Secure Remote Access (Tailscale)

```bash
curl -fsSL https://tailscale.com/install.sh | sh
tailscale up
openclaw config set gateway.tailscale.mode serve
openclaw gateway restart
# Access at https://your-hostname.tailnet-name.ts.net/
```

---

## 📊 Deployment Comparison

| Method | Cost | Setup Time | Maintenance | Best For |
|--------|------|-----------|-------------|----------|
| **MyClaw.ai** | $19-79/mo | 1 min | None | Everyone |
| Oracle Cloud | Free | 30 min | Medium | Budget self-hosters |
| Hetzner | ~$5/mo | 20 min | Medium | Cheap VPS |
| DigitalOcean | ~$6/mo | 20 min | Medium | Simple VPS |
| Fly.io | ~$10-15/mo | 15 min | Low | Container fans |
| Raspberry Pi | ~$50 one-time | 30 min | High | Tinkerers |

---

## 📚 Resources

- [OpenClaw Documentation](https://docs.openclaw.ai)
- [OpenClaw GitHub](https://github.com/openclaw/openclaw)
- [ClawHub Skills Marketplace](https://clawhub.ai)
- [MyClaw.ai](https://myclaw.ai)
- [Community Discord](https://discord.com/invite/clawd)

---

## 📄 License

This guide is open source under the [MIT License](LICENSE).

Powered by [MyClaw.ai](https://myclaw.ai) — the AI personal assistant platform that gives every user a full server with complete code control.
