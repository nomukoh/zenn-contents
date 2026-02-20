# Zenn CLI

- [📘 How to use](https://zenn.dev/zenn/articles/zenn-cli-guide)

## 基本的な手順

- 記事の作成  
  `$ npx zenn new:article`  
  `$ npx zenn new:article --slug 記事のスラッグ --title タイトル --type idea --emoji ✨`

- プレビュー  
  `$ npx zenn preview`

- 公開  
  記事を zenn.dev 上で公開するには`published`オプションが`true`になっていることを確認したうえで、ファイルをコミットし、Zenn と連携されている GitHub リポジトリにプッシュ
  - 公開日時指定
    `published_at: 2050-06-12 09:03`

## 導入手順

- フォルダ構成

  ```
  articles/
  ├─ .devcontainer/
  │    └─ devcontainer.json  # コンテナ設定ファイル
  ├─ zenn-contents/          # Zenn記事用ディレクトリ (Gitリポジトリ)
  └─ qiita-contents/         # Qiita記事用ディレクトリ (Gitリポジトリ)
  ```

- `devcontainer.json`
  ファイルを作成して `articles/` をVSCodeで開き，必要なパッケージ（`Dev Containers`）をインストールすれば完了．

  ```
  {
  "name": "Zenn & Qiita Writing Env",
  "image": "mcr.microsoft.com/devcontainers/javascript-node:24",
  "customizations": {
      "vscode": {
      "settings": {
          "terminal.integrated.defaultProfile.linux": "bash"
      },
      "extensions": [
          "ms-vscode.live-server",
          "esbenp.prettier-vscode",
          "donjayamanne.githistory"
      ]
      }
  }
  }
  ```

- `zenn-contents/` 内
  1.  新規作成する場合

  ```
  cd zenn-contents
  npm init --yes
  npm install zenn-cli
  npx zenn init
  ```

  2.  GitHubからインストールした場合

  ```
  cd zenn-contents
  npm install
  ```
