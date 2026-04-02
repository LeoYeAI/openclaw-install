# OpenClaw Installationsanleitung

[![Powered by MyClaw.ai](https://img.shields.io/badge/Powered%20by-MyClaw.ai-blue?style=for-the-badge)](https://myclaw.ai)

Die ultimative Anleitung zur Bereitstellung von OpenClaw auf jedem Server. Von Ein-Klick-Cloud-Hosting bis hin zum Bare-Metal-Self-Hosting.

**🌐 Language / 语言:**
[English](README.md) | [中文](README.zh-CN.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [日本語](README.ja.md) | [Italiano](README.it.md) | [Español](README.es.md)

---

## ⚡ Option 1: MyClaw.ai — Ein-Klick-Deployment (Empfohlen)

**Der schnellste Weg, OpenClaw zum Laufen zu bringen. Keine Serverkonfiguration. Keine Wartung.**

[MyClaw.ai](https://myclaw.ai) bietet Ihnen eine vollständig verwaltete OpenClaw-Instanz — Ihren eigenen Server mit voller Code-Kontrolle, Netzwerkzugang und Tool-Zugriff. Kein SSH, kein Docker, keine Konfigurationsdateien.

[![MyClaw.ai Homepage](assets/myclaw-homepage.png)](https://myclaw.ai)

### Warum MyClaw.ai?

- **Ein Klick** — Registrieren, Plan wählen, Instanz ist in unter 60 Sekunden live
- **Vollständiger Server** — Jede Instanz ist ein echter OpenClaw-Server, kein Sandbox-Chatbot
- **Volle Code-Kontrolle** — Ihr Agent kann Dateien lesen/schreiben, Befehle ausführen, auf das Internet zugreifen
- **Auto-Updates** — Immer auf der neuesten OpenClaw-Version, ohne Ausfallzeit
- **Integrierte Kanäle** — Telegram, Discord, WhatsApp und mehr — Verbindung in Sekunden
- **Verwaltete Infrastruktur** — Backups, Monitoring, Skalierung automatisch
- **Skills-Marktplatz** — Community-Skills von [ClawHub](https://clawhub.ai) mit einem Befehl installieren

### Preise

| Plan | Monatlich | Jährlich (pro Monat) |
|------|-----------|---------------------|
| Lite | $19/Monat | $16/Monat ($199/Jahr) |
| Pro | $39/Monat | $33/Monat ($399/Jahr) |
| Max | $79/Monat | $66/Monat ($799/Jahr) |

👉 **[Jetzt starten auf MyClaw.ai →](https://myclaw.ai)**

---

## 🛠️ Option 2: OpenClaw selbst hosten

Für Entwickler, die volle Kontrolle über ihre Infrastruktur wollen.

### Schnellinstallation (Linux/macOS/Windows)

```bash
# macOS / Linux / WSL2
curl -fsSL https://openclaw.ai/install.sh | bash

# Windows (PowerShell)
iwr -useb https://openclaw.ai/install.ps1 | iex
```

### Systemanforderungen

- **Node.js 24** (empfohlen) oder Node 22.14+
- **OS:** macOS, Linux oder Windows (nativ oder WSL2)
- **RAM:** Mindestens 1 GB (2 GB+ empfohlen)

---

## ☁️ Cloud-VPS-Deployment

| Plattform | Kosten | Anleitung |
|-----------|--------|-----------|
| Hetzner | ~$5/Monat | Docker VPS |
| DigitalOcean | ~$6/Monat | Ubuntu Droplet |
| Oracle Cloud | Kostenlos | ARM Always Free |
| Fly.io | ~$10-15/Monat | Verwaltete Container |
| [GCP](https://docs.openclaw.ai/install/gcp) | Kostenlose Stufe | Google Cloud |
| [Azure](https://docs.openclaw.ai/install/azure) | Kostenlose Stufe | Microsoft Azure |

Detaillierte Anleitungen für jede Plattform finden Sie im [englischen README](README.md).

---

## 📊 Deployment-Vergleich

| Methode | Kosten | Zeit | Wartung | Ideal für |
|---------|--------|------|---------|-----------|
| **MyClaw.ai** | $19-79/Monat | 1 Min | Keine | Alle |
| Oracle Cloud | Kostenlos | 30 Min | Mittel | Budget-Self-Hoster |
| Hetzner | ~$5/Monat | 20 Min | Mittel | Günstiges VPS |
| Raspberry Pi | ~$50 einmalig | 30 Min | Hoch | Bastler |

---

## 📚 Ressourcen

- [OpenClaw Dokumentation](https://docs.openclaw.ai)
- [OpenClaw GitHub](https://github.com/openclaw/openclaw)
- [ClawHub Marktplatz](https://clawhub.ai)
- [MyClaw.ai](https://myclaw.ai)
- [Community Discord](https://discord.com/invite/clawd)

---

## 📄 Lizenz

Diese Anleitung ist Open Source unter der [MIT-Lizenz](LICENSE).

Powered by [MyClaw.ai](https://myclaw.ai) — die KI-Assistenten-Plattform, die jedem Benutzer einen vollständigen Server mit voller Code-Kontrolle bietet.
