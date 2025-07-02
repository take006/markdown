# Tailwindcss
簡単にTailwindcssのスタイルを適応するにはCDNが便利です。このコードをHTMLファイルに読み込むだけでTailwindcssが使用できます。あくまでローカル環境での動作限定なので、本番のサーバー環境では、動作しません。本番環境にアップロードするには、ローカルにNode.jsをインストールしてTailwindcssコードを通常のCSSコードにビルドします。そしてビルド済みのCSSコードを本番サーバーにアップロードします。実際には、ビルドした通常のCSSファイルを使用してスタイルを適応するということです。
## サンプルスタイル
### grid
### grid-cols-3
### mt-8
margin-top
0.25rem*8
2rem
### p-6
padding

## CDN
Node.jsなどのセットアップをしなくても以下のコードを1行挿入するだけでTailwindcssが使用できます。しかしホットリロード機能や本番サーバーでの動作はできません。
<br>CDNで動作しているのでローカル環境側でTailwindcss⇒ノーマルCSSに変換することはできません。開発中には都度リロードしないとスタイルが反映されません。
```html
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
```
**公式サイト**<br>
https://tailwindcss.com/docs/installation/play-cdn
## Node.js
```cmd
//プロジェクトファイルに移動する
C:/Users/yuyal/Local Sites/difanime/app/public/wp-content/themes/difAnime
```
```cmd
//コマンドを実行してpakage.jsonを初期化する
npm init -y
```
```cmd
//pakage-lock.jsonを作成
npm install -D tailwindcss postcss autoprefixer
```
```cmd
npx tailwindcss init -p

//絶対パス指定バージョン
npx tailwindcss-cli@latest init -p
```
```cmd
npm run dev
```
postcss.config.js
tailwind.config.js