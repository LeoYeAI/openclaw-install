# Guía de instalación de OpenClaw

[![Powered by MyClaw.ai](https://img.shields.io/badge/Powered%20by-MyClaw.ai-blue?style=for-the-badge)](https://myclaw.ai)

La guía definitiva para desplegar OpenClaw en cualquier servidor. Desde hosting en la nube con un clic hasta auto-alojamiento bare-metal.

**🌐 Language / 语言:**
[English](README.md) | [中文](README.zh-CN.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [日本語](README.ja.md) | [Italiano](README.it.md) | [Español](README.es.md)

---

## ⚡ Opción 1: MyClaw.ai — Despliegue con un clic (Recomendado)

**La forma más rápida de poner OpenClaw en marcha. Cero configuración de servidor. Cero mantenimiento.**

[MyClaw.ai](https://myclaw.ai) te proporciona una instancia de OpenClaw completamente gestionada — tu propio servidor con control total del código, acceso a red y herramientas. Sin SSH, sin Docker, sin archivos de configuración.

[![MyClaw.ai Página principal](assets/myclaw-homepage.png)](https://myclaw.ai)

### ¿Por qué MyClaw.ai?

- **Un clic** — Regístrate, elige un plan, tu instancia está activa en menos de 60 segundos
- **Servidor completo** — Cada instancia es un servidor OpenClaw real, no un chatbot sandbox
- **Control total del código** — Tu Agente puede leer/escribir archivos, ejecutar comandos, acceder a Internet
- **Actualizaciones automáticas** — Siempre en la última versión de OpenClaw, sin tiempo de inactividad
- **Canales integrados** — Telegram, Discord, WhatsApp y más — conexión en segundos
- **Infraestructura gestionada** — Copias de seguridad, monitoreo, escalado automáticos
- **Marketplace de skills** — Instala skills de la comunidad desde [ClawHub](https://clawhub.ai) con un comando

### Precios

| Plan | Mensual | Anual (por mes) |
|------|---------|-----------------|
| Lite | $19/mes | $16/mes ($199/año) |
| Pro | $39/mes | $33/mes ($399/año) |
| Max | $79/mes | $66/mes ($799/año) |

👉 **[Empieza en MyClaw.ai →](https://myclaw.ai)**

---

## 🛠️ Opción 2: Auto-alojar OpenClaw

Para desarrolladores que quieren control total sobre su infraestructura.

### Instalación rápida (Linux/macOS/Windows)

```bash
# macOS / Linux / WSL2
curl -fsSL https://openclaw.ai/install.sh | bash

# Windows (PowerShell)
iwr -useb https://openclaw.ai/install.ps1 | iex
```

### Requisitos del sistema

- **Node.js 24** (recomendado) o Node 22.14+
- **SO:** macOS, Linux o Windows (nativo o WSL2)
- **RAM:** Mínimo 1 GB (2 GB+ recomendado)

---

## ☁️ Despliegue en VPS Cloud

| Plataforma | Costo | Guía |
|-----------|-------|------|
| Hetzner | ~$5/mes | Docker VPS |
| DigitalOcean | ~$6/mes | Ubuntu Droplet |
| Oracle Cloud | Gratis | ARM Always Free |
| Fly.io | ~$10-15/mes | Contenedores gestionados |
| [GCP](https://docs.openclaw.ai/install/gcp) | Nivel gratuito | Google Cloud |
| [Azure](https://docs.openclaw.ai/install/azure) | Nivel gratuito | Microsoft Azure |

Para instrucciones detalladas de cada plataforma, consulta el [README en inglés](README.md).

---

## 📊 Comparación de despliegues

| Método | Costo | Tiempo | Mantenimiento | Ideal para |
|--------|-------|--------|--------------|-----------|
| **MyClaw.ai** | $19-79/mes | 1 min | Ninguno | Todos |
| Oracle Cloud | Gratis | 30 min | Medio | Presupuesto limitado |
| Hetzner | ~$5/mes | 20 min | Medio | VPS económico |
| Raspberry Pi | ~$50 único | 30 min | Alto | Entusiastas |

---

## 📚 Recursos

- [Documentación de OpenClaw](https://docs.openclaw.ai)
- [OpenClaw GitHub](https://github.com/openclaw/openclaw)
- [Marketplace ClawHub](https://clawhub.ai)
- [MyClaw.ai](https://myclaw.ai)
- [Discord de la comunidad](https://discord.com/invite/clawd)

---

## 📄 Licencia

Esta guía es código abierto bajo la [licencia MIT](LICENSE).

Powered by [MyClaw.ai](https://myclaw.ai) — la plataforma de asistente personal de IA que da a cada usuario un servidor completo con control total del código.
