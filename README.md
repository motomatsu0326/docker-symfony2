# docker-symfony2
dockerでSymfony2.8の開発環境を構築

## 環境構築手順
※ 前提条件：Docker, Docker Composeを導入済みであること

①postgresデータ出力ディレクトリのgitkeepを削除(削除しないとコンテナ作成時にエラーになる)
```
rm docker/postgres/data/.gitkeep
```

②コンテナーを作成し実行
```
$ docker-compose up -d
```

③Webサーバーのコンテナーに接続
```
$ docker exec -it [リポジトリ名]_web_1 bash
```

④コンテナー内で依存ライブラリをインストール
```
$ composer install
$ exit
```

⑤下記URLに接続確認
```
http://localhost:8080/web
```

⑥下記URLにアクセスしてMailCatcher（メールサーバー）に接続確認
```
http://localhost:1080
```

⑦下記URLにアクセスしてadminer（db管理ツール）に接続確認
```
http://localhost:8081
```
※データベースの接続情報は下記の通り
| 設定項目 | 設定値 |
| :---: | :---: |
| データーベース種別 | PostgreSQL |
| サーバー | db |
| ユーザー名 | postgres |
| パスワード | postgres |
| データベース | symfony |
