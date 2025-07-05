標準的なPHPで推奨するディレクトリ構造は位階の通り。

```
/
├── public/
│   ├── index.php         # すべてのリクエストがここを経由するフロントコントローラ
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js
│   ├── images/
│   │   └── logo.png
│   └── .htaccess         # URLのリライト設定（Apacheの場合）
├── src/
│   ├── Controllers/      # ページのロジックを処理するコントローラ
│   │   └── HomeController.php
│   ├── Models/           # データベース操作やビジネスロジックを扱うモデル
│   │   └── User.php
│   ├── Views/            # HTMLテンプレート
│   │   ├── home.php
│   │   └── layouts/
│   │       └── default.php
│   ├── Config/           # データベース接続情報などの設定ファイル
│   │   └── database.php
│   ├── Helpers/          # 汎用的な関数など
│   │   └── functions.php
│   └── bootstrap.php     # アプリケーションの初期化処理
├── vendor/               # Composerでインストールしたライブラリ（Composerを使用する場合）
├── .env                  # 環境変数（データベース接続情報など、本番と開発で異なる情報）
├── composer.json         # Composerの設定ファイル（Composerを使用する場合）
├── composer.lock         # Composerの依存関係ロックファイル（Composerを使用する場合）
└── README.md             # プロジェクトの説明
```