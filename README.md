# docker-symfony2
dockerでSymfony2.8の開発環境を構築

## 環境構築手順
※ 前提条件：Docker, Docker Composeを導入済みであること

①コンテナーを作成し実行
```
$ docker-compose up -d
```

②Webサーバーのコンテナーに接続
```
$ docker exec -it docker-symfony2_web_1 bash
```

③コンテナー内で依存ライブラリをインストール
```
$ composer install
$ exit
```

④下記URLに接続してEC-CUBEの初期設定
```
http://localhost:8888/web
```

⑤下記URLにアクセスしてMailCatcher（メールサーバー）に接続確認
```
http://localhost:1080/
```

④ 下記URLにアクセスしてadminer（db管理ツール）に接続確認
```
http://localhost:8089
```
