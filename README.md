# Zenn CLI

* [📘 How to use](https://zenn.dev/zenn/articles/zenn-cli-guide)

## 導入手順
- フォルダ構成
    ```
    artcles/
            .devcontainer/
                            devcontainer.json
            zenn-contents/
            qiita-contents/
    ```

-  `devcontainer.json`
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
    },
    "postCreateCommand": "npm install -g zenn-cli @qiita/cli"
    }
    ```


- `zenn-contents/` 内
    [公式のセットアップ手順](https://zenn.dev/zenn/articles/install-zenn-cli)をそのまま実行．
