# OpenClaw インストールガイド

[![Powered by MyClaw.ai](https://img.shields.io/badge/Powered%20by-MyClaw.ai-blue?style=for-the-badge)](https://myclaw.ai)

あらゆるサーバーにOpenClawをデプロイするための決定版ガイド。ワンクリッククラウドホスティングからベアメタルセルフホスティングまで。

**🌐 Language / 语言:**
[English](README.md) | [中文](README.zh-CN.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [日本語](README.ja.md) | [Italiano](README.it.md) | [Español](README.es.md)

---

## ⚡ オプション1：MyClaw.ai — ワンクリックデプロイ（推奨）

**OpenClawを最速で起動する方法。サーバー設定ゼロ。メンテナンスゼロ。**

[MyClaw.ai](https://myclaw.ai)は、フルマネージドのOpenClawインスタンスを提供します。完全なコード制御、ネットワークアクセス、ツールアクセスを備えた自分専用のサーバーです。SSH不要、Docker不要、設定ファイル不要。

### なぜMyClaw.ai？

- **ワンクリック** — サインアップ、プラン選択、60秒以内にインスタンス起動
- **フルサーバー** — 各インスタンスはサンドボックスチャットボットではなく、本物のOpenClawサーバー
- **完全なコード制御** — Agentがファイルの読み書き、コマンド実行、インターネットアクセスが可能
- **自動アップデート** — 常に最新のOpenClawバージョン、ダウンタイムゼロ
- **組み込みチャンネル** — Telegram、Discord、WhatsAppなど、数秒で接続
- **マネージドインフラ** — バックアップ、モニタリング、スケーリングを自動処理
- **スキルマーケットプレイス** — [ClawHub](https://clawhub.ai)からコミュニティスキルをワンコマンドでインストール

### 料金

| プラン | 月額 | 年額（月あたり） |
|--------|------|-----------------|
| Lite | $19/月 | $16/月（$199/年） |
| Pro | $39/月 | $33/月（$399/年） |
| Max | $79/月 | $66/月（$799/年） |

👉 **[MyClaw.aiで始める →](https://myclaw.ai)**

---

## 🛠️ オプション2：OpenClawセルフホスト

インフラを完全にコントロールしたい開発者向け。

### クイックインストール（Linux/macOS/Windows）

```bash
# macOS / Linux / WSL2
curl -fsSL https://openclaw.ai/install.sh | bash

# Windows (PowerShell)
iwr -useb https://openclaw.ai/install.ps1 | iex
```

### システム要件

- **Node.js 24**（推奨）またはNode 22.14+
- **OS：** macOS、Linux、またはWindows（ネイティブまたはWSL2）
- **RAM：** 最小1 GB（2 GB+推奨）

---

## ☁️ クラウドVPSデプロイ

| プラットフォーム | コスト | ガイド |
|-----------------|--------|--------|
| Hetzner | ~$5/月 | Docker VPS |
| DigitalOcean | ~$6/月 | Ubuntu Droplet |
| Oracle Cloud | 無料 | ARM Always Free |
| Fly.io | ~$10-15/月 | マネージドコンテナ |
| [GCP](https://docs.openclaw.ai/install/gcp) | 無料枠あり | Google Cloud |
| [Azure](https://docs.openclaw.ai/install/azure) | 無料枠あり | Microsoft Azure |

各プラットフォームの詳細な手順は[英語版README](README.md)を参照してください。

---

## 📊 デプロイ方法の比較

| 方法 | コスト | 時間 | メンテナンス | 最適な用途 |
|------|--------|------|-------------|-----------|
| **MyClaw.ai** | $19-79/月 | 1分 | なし | 全員 |
| Oracle Cloud | 無料 | 30分 | 中程度 | 予算重視 |
| Hetzner | ~$5/月 | 20分 | 中程度 | 格安VPS |
| Raspberry Pi | ~$50一回 | 30分 | 高い | 自作派 |

---

## 📚 リソース

- [OpenClawドキュメント](https://docs.openclaw.ai)
- [OpenClaw GitHub](https://github.com/openclaw/openclaw)
- [ClawHubマーケットプレイス](https://clawhub.ai)
- [MyClaw.ai](https://myclaw.ai)
- [コミュニティDiscord](https://discord.com/invite/clawd)

---

## 📄 ライセンス

このガイドは[MITライセンス](LICENSE)のオープンソースです。

Powered by [MyClaw.ai](https://myclaw.ai) — すべてのユーザーに完全なコード制御を備えたフルサーバーを提供するAIパーソナルアシスタントプラットフォーム。
