# AI開発環境 - AI Development Container

## 概要

このプロジェクトは、AI開発とマルチ言語プログラミングに最適化されたDevContainer環境です。Claude Code、Python、Node.js、Java、そして豊富な開発ツールが統合された包括的な開発環境を提供します。

## 🚀 主な特徴

- **AI統合開発**: Claude CodeとGemini CLIによる高度なAI支援開発
- **マルチ言語サポート**: Python 3.11、Node.js LTS、Java 17
- **豊富な拡張機能**: 60以上のVSCode拡張機能を事前インストール
- **即座に使える環境**: コンテナ起動後すぐに開発開始可能
- **ポート転送設定**: Django、Spring Boot、Streamlitアプリケーション対応

## 📋 前提条件

以下のソフトウェアがインストールされている必要があります：

- [Rancher Desktop](https://rancherdesktop.io/) (Docker Desktopの代替として推奨)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Dev Containers拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## 🛠️ インストールされるツール・言語

### プログラミング言語
- **Python 3.11**: Django、FastAPI、Streamlit、機械学習ライブラリ対応
- **Node.js LTS**: 最新の長期サポート版
- **Java 17**: Maven、Gradle統合

### AI・機械学習ツール
- **Claude Code**: Anthropic製AI開発支援ツール
- **Gemini CLI**: Google製AI開発支援ツール
- **LightGBM**: 高性能勾配ブースティングフレームワーク
- **Jupyter**: データサイエンス・機械学習開発

### Webフレームワーク
- **Django**: Python Webフレームワーク
- **FastAPI**: 高性能Python APIフレームワーク
- **Streamlit**: データアプリケーション構築

### 開発ツール
- **Zsh + Oh My Zsh**: 高機能シェル環境
- **Git**: バージョン管理
- **PlantUML**: UML図作成
- **Draw.io**: 図表作成

## 📦 VSCode拡張機能

### 一般開発
- Markdown Preview Enhanced
- Markdown All in One
- PlantUML
- YAML Language Support
- Draw.io Integration
- Code Spell Checker

### フロントエンド開発
- HTML Preview
- TypeScript
- Vue.js (Volar)
- HTML Language Features

### バックエンド開発
- **Java**: Extension Pack、Spring Boot Dashboard、Spring Initializr
- **Python**: Python、Flake8、Black Formatter、Django、Jupyter、Pylint

### AI・データベース
- Roo Cline (AI Agent)
- Google - Gemini
- Database Client

## 🚀 セットアップ手順

### 1. リポジトリのクローン
```bash
git clone <repository-url>
cd ai-development
```

### 2. Dev Containerで開く
1. Visual Studio Codeでプロジェクトフォルダを開く
2. コマンドパレット（`Ctrl+Shift+P` / `Cmd+Shift+P`）を開く
3. `Dev Containers: Reopen in Container` を選択
4. コンテナのビルドと起動を待つ（初回は数分かかります）

### 3. Claude Code認証
コンテナ起動後、ターミナルで以下を実行：
```bash
claude auth
```

## 🔧 環境設定詳細

### ベースイメージ
- **Ubuntu 22.04**: 安定したLinux環境

### ポート設定
| ポート | 用途 | 説明 |
|--------|------|------|
| 8000 | Django/FastAPI | Python Webアプリケーション |
| 8080 | Spring Boot | Java Webアプリケーション |
| 8501 | Streamlit | データアプリケーション |

### マウント設定
- ローカルワークスペース → `/workspace` (バインドマウント)
- 高速ファイルアクセスのためのキャッシュ最適化

### 環境変数
- `PATH`: Python local binディレクトリを追加
- デフォルトシェル: Zsh
- Python インタープリター: `/usr/local/bin/python3`
- Java ホーム: `/usr/local/sdkman/candidates/java/current`

## 💻 使用方法

### Python開発
```bash
# Django プロジェクト作成
django-admin startproject myproject

# FastAPI アプリケーション実行
uvicorn main:app --host 0.0.0.0 --port 8000

# Streamlit アプリケーション実行
streamlit run app.py --server.port 8501
```

### Java開発
```bash
# Spring Boot プロジェクト作成（VSCode拡張機能使用）
# Ctrl+Shift+P → "Spring Initializr: Generate a Maven Project"

# Maven プロジェクトビルド
mvn clean install

# Gradle プロジェクトビルド
gradle build
```

### Node.js開発
```bash
# プロジェクト初期化
npm init -y

# 依存関係インストール
npm install

# 開発サーバー起動
npm run dev
```

## 🔍 Claude Code使用方法

1. **認証**: `claude auth` コマンドで認証
2. **AI支援**: コード補完、リファクタリング、バグ修正
3. **対話型開発**: 自然言語でのコード生成・説明

## ✨ Gemini CLI使用方法

1. **生成AI**: `gemini` コマンドで起動
2. **AI支援**: コード補完、リファクタリング、バグ修正
3. **対話型開発**: 自然言語でのコード生成・説明

## 📊 プロジェクト構造

```
ai-development/
├── .devcontainer/
│   └── devcontainer.json    # Dev Container設定
├── workspace/               # 開発作業ディレクトリ
└── README.md               # このファイル
```

## 🐛 トラブルシューティング

### コンテナが起動しない
1. Rancher Desktop（またはDocker環境）が起動していることを確認
2. 十分なディスク容量があることを確認（最低5GB推奨）
3. Dev Containers拡張機能が最新版であることを確認

### ポートアクセスできない
1. ファイアウォール設定を確認
2. `docker ps` でポート転送設定を確認
3. アプリケーションが正しいホスト（0.0.0.0）でリッスンしているか確認

### Claude Code認証エラー
1. インターネット接続を確認
2. `claude auth` コマンドを再実行
3. ブラウザでの認証プロセスを完了

### Gemini CLI認証エラー
1. インターネット接続を確認
2. `gemini` コマンドを再実行
3. ブラウザでの認証プロセスを完了

### Python/Node.js/Javaコマンドが見つからない
1. コンテナを再起動: `Dev Containers: Rebuild Container`
2. パス設定を確認: `echo $PATH`
3. 該当言語の再インストール

### 拡張機能が動作しない
1. VSCodeを再起動
2. 拡張機能を無効化→有効化
3. コンテナを再ビルド

## 🔄 アップデート

### Dev Container設定更新
1. `.devcontainer/devcontainer.json` を編集
2. `Dev Containers: Rebuild Container` を実行

### 依存関係更新
```bash
# Python パッケージ更新
pip install --upgrade pip
pip install --upgrade <package-name>

# Node.js パッケージ更新
npm update

# Java依存関係更新（Maven）
mvn versions:use-latest-versions
```

## 📝 カスタマイズ

### 追加パッケージインストール
[`devcontainer.json`](.devcontainer/devcontainer.json:80)の`postCreateCommand`を編集：

```json
"postCreateCommand": "pip install --upgrade pip && pip install django fastapi streamlit uvicorn LightGBM your-package && npm install -g @google/gemini-cli your-npm-package"
```

### VSCode拡張機能追加
[`devcontainer.json`](.devcontainer/devcontainer.json:31-63)の`extensions`配列に追加：

```json
"extensions": [
  "existing.extension",
  "new.extension-id"
]
```

### ポート設定変更
[`devcontainer.json`](.devcontainer/devcontainer.json:94-110)の`forwardPorts`と`portsAttributes`を編集

## 🤝 貢献

1. このリポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add amazing feature'`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

## 📄 ライセンス

このプロジェクトは MIT ライセンスの下で公開されています。

## 🆘 サポート

問題や質問がある場合は、以下の方法でサポートを受けることができます：

1. **Issues**: GitHubのIssuesページで問題を報告
2. **Discussions**: 一般的な質問や議論
3. **Documentation**: このREADMEファイルを参照

---

**Happy Coding with AI! 🤖✨**