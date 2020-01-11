# Prologue

## 環境

### ミドルウェア

- php 7.3.3
- nginx 1.17.7
- mysql 8.0.18


- Laravel 6.10.1

### Docker

- app: バックエンドのAPI（php 7.3.3）
- web: Webサーバー（nginx 1.17.7）
- db: DB（MySQL 8.0.18）

## 起動

### 各コンテナのビルド（初めて起動する時）

```bash
# 設定ファイルの作成
$ cp .env.default .env
$ docker-compose build
```

### 各コンテナの起動

```bash
$ docker-compose up
```

### DBセットアップ

```bash
$ docker-compose exec app php artisan migrate
```

### ひとつのコンテナの再起動

```bash
$ docker-compose restart app
```

## テスト

### php_cs_fixer

```bash
$ docker exec app composer fixer
# また`-fix`をつけると自動整形
$ docker exec app composer fixer-fix
```

## MySQL 接続

```bash
$ docker-compose exec db bash -c 'mysql -u${MYSQL_USER} -p${MYSQL_PASSWORD} ${MYSQL_DATABASE}'
```
