# Laravel SailとLaravel




## DockerとLaravel
- **Docker**は、コンテナを構築・実行するための**基盤となる技術**。
- **Laravel Sail**は、そのDockerという技術を使い、**Laravel開発に必要な環境を「簡単に」「統合的に」構築・管理するためのツール**。
- DockerをLaravelようにカスタマイズしているため、自由度の高くハードルが高いDockerを簡単に導入出来て、簡易化されたコマンドで操作も完結できる

# Laravel Sail
- Laravel Sailは、**Laravelアプリケーションのために特別に作られた、Dockerを利用した開発環境管理ツール**です。
- Dockerそのものではなく、**DockerをLaravel開発のために使いやすくするための「ラッパー（Wrapper）」または「ヘルパー」**のようなものです。

***Docker Composeファイル***

- Laravel Sailの内部では、実際にはDocker Compose（複数のDockerコンテナを連携させて管理するDockerのツール）が利用されています。Laravel Sailは、このDocker Composeの設定ファイルを事前に用意し、それを簡単に操作するための `./vendor/bin/sail` コマンドを提供します。

***`./vendor/bin/sail`コマンド***

- このコマンド体系はLaravel開発者が直感的に使えるように設計されており、例えば `sail artisan` でコンテナ内のArtisanコマンドを実行したり、`sail test` でテストを実行したりできます。



つまり、Laravel Sailは、Dockerという強力なツールをLaravel開発者が意識することなく、スムーズに利用できるように抽象化・簡略化してくれているシステムなのです。これにより、Dockerの複雑なコマンドを覚えることなく、すぐにLaravel開発に取り掛かれるようになっています。

***Docker Compose***
docker-compose.ymlがLaravelに最適化された状態でセットアップされる。セットアップされているのでユーザーはLaravel Sailのwrapperコマンドを使用して直感的にコンテナを操作できる。

```
php artisan sail:install
```
で自動的に設定ファイルdocker-compose.ymlが生成される

***使用方法の違い***

ノーマルのDockerの場合`docker-compose`を直接使用し、Laravel Sail`./vendor/bin/sail`を使用する
Docker Composeの設定ファイルを編集することで、必要に応じて追加のサービス（例: メッセージキュー、検索エンジンなど）を簡単に追加・設定できます。

SailのDocker Compose設定でPHPのバージョンを指定できるため、手動でPHPのバージョンを切り替える必要もありません。

Laravel Sailの内部では、実際にはDocker Compose（複数のDockerコンテナを連携させて管理するDockerのツール）が利用されています。Laravel Sailは、このDocker Composeの設定ファイル(Laravel用にカスタマイズされている)を事前に用意し、それを簡単に操作するための `./vendor/bin/sail` コマンドを提供します。

## Laravel Sailのメリット
**PHP,Nginx,データベース,Redisが一度に起動する**

# Laravel
***Artisanコマンド***

Laravelに組み込まれている強力なCLI(標準)

データベースにおいてテーブル作成、変更などLaravelで行う多くのタスクをコマンドで完結できる。

Laravel SailでもArtisanコマンドは実行できるように設計されている。

**Laravel版**

```bash
php artisan migrate
```

**Laravel Sail版**

```bash
./vendor/bin/sail artisan migrate
```

Sail artisanコマンドは裏側でPHPコンテナに入ってコンテナ内で実行してくれている。コンテナ内のPHPを使って実行しているのでローカルにPHPのインストールは不要。

インストールする手間もなくコンテナの構築さえ行えば、別PCでも同じ環境で開発ができる。

Laravel開発で必要不可欠なArtisanコマンドをDockerizedされた環境でも実行できるように橋渡しをしてくれている。

# ComposerとDocker（Laravel Sail）

**ローカルPC側**

1. Composerをインストール(公式からのインストール、WSL2側でコマンド操作でもインストールできる)
2. WSL2をインストールする
3. Docker Desktopをインストールする

ComposerでLaravelプロジェクトを作成して、その流れでLaravel Sailも同時に導入する。

Laravel Sailに必要なDocker Composeの設定ファイルがダウンロードされる。

Laravel Sailのプロジェクトファイルの./vendor/binフォルダに格納されているコマンドを実行する。

***Composerのインストール先***

WSL2にインストールすべき

Docker DesktopがWSL2環境下で動作する、PHP特にLaravelのようなフレームワークはLinux環境サーバーにデプロイされるため、環境が一致している方が良い。

## 他の開発環境
使用することが多いXAMPP（MacはMAMP）とLaravel Sailの違いです。
| 比較項目 | ローカルに直接インストール (例: PHP, Apache, MySQLを個別にインストール) | MAMP/XAMPPなど (パッケージ化されたローカルサーバー) | Laravel Sail (Dockerベース) |  |
| --- | --- | --- | --- | --- |
| セットアップ | 手動で複雑。依存関係の解決が大変。 | 比較的簡単だが、OSごとに差異がある。 | 非常に簡単。コマンド一つで環境構築。 |  |
| 環境の統一性 | 低い。開発者間で差異が出やすい。 | 低い。OSやバージョンで差異が出やすい。 | 高い。Dockerにより完全に統一された環境。 |  |
| OS汚染 | 高い。様々なソフトウェアがOSにインストールされる。 | 中程度。ある程度のソフトウェアがOSにインストールされる。 | 低い。すべてコンテナ内に隔離される。 |  |
| 複数PJ管理 | 難しい。バージョン衝突の問題が出やすい。 | 難しい。バージョン衝突の問題が出やすい。 | 容易。各PJが独立した環境を持つ。 |  |
| 本番近似 | 低い。本番環境との差異が大きい。 | 低い。 | 高い。コンテナ技術のため本番と近い環境を構築できる。 |  |
| 学習コスト | 初期は低いが、問題発生時に原因究明が難しい。 | 低い。 | Dockerの基礎知識は必要だが、長期的にメリット大。 |  |
|  |  |  |  |  |