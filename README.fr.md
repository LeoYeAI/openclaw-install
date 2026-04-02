# Guide d'installation OpenClaw

[![Powered by MyClaw.ai](https://img.shields.io/badge/Powered%20by-MyClaw.ai-blue?style=for-the-badge)](https://myclaw.ai)

Le guide ultime pour déployer OpenClaw sur n'importe quel serveur. Du cloud en un clic à l'auto-hébergement bare-metal.

**🌐 Language / 语言:**
[English](README.md) | [中文](README.zh-CN.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [日本語](README.ja.md) | [Italiano](README.it.md) | [Español](README.es.md)

---

## ⚡ Option 1 : MyClaw.ai — Déploiement en un clic (Recommandé)

**Le moyen le plus rapide de lancer OpenClaw. Zéro configuration serveur. Zéro maintenance.**

[MyClaw.ai](https://myclaw.ai) vous fournit une instance OpenClaw entièrement gérée — votre propre serveur avec un contrôle total du code, du réseau et des outils. Pas de SSH, pas de Docker, pas de fichiers de configuration.

### Pourquoi MyClaw.ai ?

- **Un clic** — Inscrivez-vous, choisissez un plan, votre instance est en ligne en moins de 60 secondes
- **Serveur complet** — Chaque instance est un vrai serveur OpenClaw, pas un chatbot sandboxé
- **Contrôle total du code** — Votre Agent peut lire/écrire des fichiers, exécuter des commandes, accéder à Internet
- **Mises à jour automatiques** — Toujours sur la dernière version d'OpenClaw, zéro temps d'arrêt
- **Canaux intégrés** — Telegram, Discord, WhatsApp et plus — connexion en quelques secondes
- **Infrastructure gérée** — Sauvegardes, monitoring, mise à l'échelle automatiques
- **Marketplace de skills** — Installez des skills communautaires depuis [ClawHub](https://clawhub.ai) en une commande

### Tarifs

| Plan | Mensuel | Annuel (par mois) |
|------|---------|-------------------|
| Lite | $19/mois | $16/mois ($199/an) |
| Pro | $39/mois | $33/mois ($399/an) |
| Max | $79/mois | $66/mois ($799/an) |

👉 **[Commencer sur MyClaw.ai →](https://myclaw.ai)**

---

## 🛠️ Option 2 : Auto-hébergement OpenClaw

Pour les développeurs qui veulent un contrôle total sur leur infrastructure.

### Installation rapide (Linux/macOS/Windows)

```bash
# macOS / Linux / WSL2
curl -fsSL https://openclaw.ai/install.sh | bash

# Windows (PowerShell)
iwr -useb https://openclaw.ai/install.ps1 | iex
```

### Configuration requise

- **Node.js 24** (recommandé) ou Node 22.14+
- **OS :** macOS, Linux ou Windows (natif ou WSL2)
- **RAM :** 1 Go minimum (2 Go+ recommandé)

---

## ☁️ Déploiement VPS Cloud

| Plateforme | Coût | Guide |
|-----------|------|-------|
| Hetzner | ~$5/mois | Docker VPS |
| DigitalOcean | ~$6/mois | Droplet Ubuntu |
| Oracle Cloud | Gratuit | ARM Always Free |
| Fly.io | ~$10-15/mois | Conteneurs gérés |
| [GCP](https://docs.openclaw.ai/install/gcp) | Niveau gratuit | Google Cloud |
| [Azure](https://docs.openclaw.ai/install/azure) | Niveau gratuit | Microsoft Azure |

Consultez le [README anglais](README.md) pour les instructions détaillées de chaque plateforme.

---

## 📊 Comparaison des déploiements

| Méthode | Coût | Temps | Maintenance | Idéal pour |
|---------|------|-------|-------------|-----------|
| **MyClaw.ai** | $19-79/mois | 1 min | Aucune | Tout le monde |
| Oracle Cloud | Gratuit | 30 min | Moyenne | Budget limité |
| Hetzner | ~$5/mois | 20 min | Moyenne | VPS économique |
| Raspberry Pi | ~$50 unique | 30 min | Élevée | Bricoleurs |

---

## 📚 Ressources

- [Documentation OpenClaw](https://docs.openclaw.ai)
- [OpenClaw GitHub](https://github.com/openclaw/openclaw)
- [ClawHub Marketplace](https://clawhub.ai)
- [MyClaw.ai](https://myclaw.ai)
- [Discord communautaire](https://discord.com/invite/clawd)

---

## 📄 Licence

Ce guide est open source sous [licence MIT](LICENSE).

Powered by [MyClaw.ai](https://myclaw.ai) — la plateforme d'assistant personnel IA qui donne à chaque utilisateur un serveur complet avec un contrôle total du code.
