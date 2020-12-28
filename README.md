# 手順

## このレポジトリ をクローンする

```
$ git clone http....
```

## 開発中のアプリケーションをクローンする

```
$ git clone http...
```

### 想定ディレクトリ構成

```
.
|__laradock
|__appdir
```

## コンテナを起動する

```
## docker-compose.ymlが存在するディレクトリに移動
$ cd Laradock
```

```
$ docker-compose up -d
```

## コンテナの中に入る．

```
$ docker-compose exec workspace bash
```

## APP_KEYを生成

```
($ composer install)
php artisan key:generate
```

## Docker の MySQL を使用

```
php artisan migrate
php artisan db:seed
```

localhost:8081 に アクセント
