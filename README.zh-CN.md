# OpenClaw 安装部署指南

[![Powered by MyClaw.ai](https://img.shields.io/badge/Powered%20by-MyClaw.ai-blue?style=for-the-badge)](https://myclaw.ai)

OpenClaw 服务器部署的终极指南。从一键云托管到裸机自建，全覆盖。

**🌐 Language / 语言:**
[English](README.md) | [中文](README.zh-CN.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [日本語](README.ja.md) | [Italiano](README.it.md) | [Español](README.es.md)

---

## ⚡ 方案一：MyClaw.ai — 一键部署（推荐）

**最快上手 OpenClaw 的方式。零服务器配置，零运维。**

[MyClaw.ai](https://myclaw.ai) 为你提供全托管的 OpenClaw 实例——你自己的服务器，拥有完整的代码控制权、网络访问和工具调用能力。无需 SSH，无需 Docker，无需配置文件。

### 为什么选 MyClaw.ai？

- **一键启动** — 注册、选套餐，60 秒内实例上线
- **完整服务器** — 每个实例都是真实的 OpenClaw 服务器，不是沙盒聊天机器人
- **完整代码控制** — 你的 Agent 可以读写文件、执行命令、访问互联网
- **自动更新** — 始终运行最新版 OpenClaw，零停机
- **内置频道** — Telegram、Discord、WhatsApp 等，秒级接入
- **托管基础设施** — 备份、监控、扩容全自动
- **技能市场** — 从 [ClawHub](https://clawhub.ai) 一键安装社区技能

### 定价

| 套餐 | 月付 | 年付（月均） |
|------|------|------------|
| Lite | $19/月 | $16/月（$199/年） |
| Pro | $39/月 | $33/月（$399/年） |
| Max | $79/月 | $66/月（$799/年） |

👉 **[立即开始 → MyClaw.ai](https://myclaw.ai)**

---

## 🛠️ 方案二：自建 OpenClaw

适合想完全掌控基础设施的开发者。选择你的平台：

### 快速安装（Linux/macOS/Windows 通用）

```bash
# macOS / Linux / WSL2
curl -fsSL https://openclaw.ai/install.sh | bash

# Windows (PowerShell)
iwr -useb https://openclaw.ai/install.ps1 | iex
```

安装脚本会自动检测系统、安装 Node.js、安装 OpenClaw 并启动引导流程。

### 系统要求

- **Node.js 24**（推荐）或 Node 22.14+
- **操作系统：** macOS、Linux 或 Windows（原生或 WSL2）
- **内存：** 最低 1 GB（推荐 2 GB+）

---

## ☁️ 云服务器部署

### Hetzner（约 $5/月）

最便宜的可靠 24/7 托管方案。

```bash
ssh root@你的服务器IP

# 安装 Docker
apt-get update && apt-get install -y git curl ca-certificates
curl -fsSL https://get.docker.com | sh

# 克隆并安装
git clone https://github.com/openclaw/openclaw.git
cd openclaw
./scripts/docker/setup.sh
```

通过 SSH 隧道访问：
```bash
ssh -N -L 18789:127.0.0.1:18789 root@你的服务器IP
# 打开 http://127.0.0.1:18789
```

### DigitalOcean（$6/月）

```bash
ssh root@你的Droplet_IP

apt update && apt upgrade -y
curl -fsSL https://deb.nodesource.com/setup_24.x | bash -
apt install -y nodejs

curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

### Oracle Cloud（免费！）

Oracle 永久免费 ARM 层：最高 4 OCPU、24 GB 内存、200 GB 存储——零成本。

```bash
ssh ubuntu@你的公网IP

sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential

curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon

# 推荐：用 Tailscale 安全远程访问
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up --ssh --hostname=openclaw
openclaw config set gateway.tailscale.mode serve
```

### Fly.io（约 $10-15/月）

托管容器，自动 HTTPS。

```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw

fly apps create my-openclaw
fly volumes create openclaw_data --size 1 --region iad
fly secrets set OPENCLAW_GATEWAY_TOKEN=$(openssl rand -hex 32)
fly secrets set ANTHROPIC_API_KEY=sk-ant-...
fly deploy
```

### 其他平台

| 平台 | 文档 | 费用 |
|------|------|------|
| [GCP](https://docs.openclaw.ai/install/gcp) | Google Cloud | 有免费额度 |
| [Azure](https://docs.openclaw.ai/install/azure) | Microsoft Azure | 有免费额度 |
| [Railway](https://docs.openclaw.ai/install/railway) | Railway | 按用量计费 |
| [Render](https://docs.openclaw.ai/install/render) | Render | 有免费额度 |
| [Northflank](https://docs.openclaw.ai/install/northflank) | Northflank | 有免费额度 |

---

## 🐳 Docker 部署

适合容器化或无头部署。

```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw

# 自动安装（推荐）
./scripts/docker/setup.sh

# 或使用预构建镜像
export OPENCLAW_IMAGE="ghcr.io/openclaw/openclaw:latest"
./scripts/docker/setup.sh
```

### Docker Compose（手动配置）

```yaml
services:
  openclaw-gateway:
    image: ghcr.io/openclaw/openclaw:latest
    restart: unless-stopped
    environment:
      - NODE_ENV=production
      - OPENCLAW_GATEWAY_TOKEN=你的密钥
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

## 🍓 树莓派

永远在线的个人 AI，硬件成本约 $50。

**要求：** 树莓派 4/5，2 GB+ 内存，64 位树莓派 OS

```bash
# 刷入 Raspberry Pi OS Lite (64-bit)，然后 SSH 连接
ssh user@gateway-host

sudo apt update && sudo apt upgrade -y
sudo apt install -y git curl build-essential

# 安装 Node.js 24
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
sudo apt install -y nodejs

# 添加 swap（2GB 内存必须）
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile && sudo mkswap /swapfile && sudo swapon /swapfile
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab

# 安装 OpenClaw
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

**建议：**
- 用 USB SSD 替代 SD 卡，性能更好
- 使用 API 模型（Claude、GPT）——不要在树莓派上跑本地模型
- 释放 GPU 内存：`echo 'gpu_mem=16' | sudo tee -a /boot/config.txt`

---

## 🔧 安装后配置

### 验证安装

```bash
openclaw --version
openclaw doctor
openclaw gateway status
```

### 接入频道

```bash
# Telegram
openclaw channels add --channel telegram --token "你的BOT_TOKEN"

# Discord
openclaw channels add --channel discord --token "你的BOT_TOKEN"

# WhatsApp（扫码）
openclaw channels login
```

### 安全远程访问（Tailscale）

```bash
curl -fsSL https://tailscale.com/install.sh | sh
tailscale up
openclaw config set gateway.tailscale.mode serve
openclaw gateway restart
# 通过 https://你的主机名.tailnet名.ts.net/ 访问
```

---

## 📊 部署方案对比

| 方案 | 费用 | 部署时间 | 运维难度 | 适合人群 |
|------|------|---------|---------|---------|
| **MyClaw.ai** | $19-79/月 | 1 分钟 | 无 | 所有人 |
| Oracle Cloud | 免费 | 30 分钟 | 中等 | 预算有限的自建者 |
| Hetzner | 约 $5/月 | 20 分钟 | 中等 | 便宜 VPS |
| DigitalOcean | 约 $6/月 | 20 分钟 | 中等 | 简单 VPS |
| Fly.io | 约 $10-15/月 | 15 分钟 | 低 | 容器爱好者 |
| 树莓派 | 约 $50 一次性 | 30 分钟 | 高 | 折腾党 |

---

## 📚 资源

- [OpenClaw 文档](https://docs.openclaw.ai)
- [OpenClaw GitHub](https://github.com/openclaw/openclaw)
- [ClawHub 技能市场](https://clawhub.ai)
- [MyClaw.ai](https://myclaw.ai)
- [社区 Discord](https://discord.com/invite/clawd)

---

## 📄 许可证

本指南以 [MIT 许可证](LICENSE) 开源。

Powered by [MyClaw.ai](https://myclaw.ai) — 给每个用户一台完整服务器的 AI 个人助手平台。
