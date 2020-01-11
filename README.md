# Prologue

## ミドルウェア

- php 7.3.3
- nginx 1.17.7
- mysql 8.0.18

- Laravel 6.10.1

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

### MySQL 接続

```bash
$ docker-compose exec db bash -c 'mysql -u${MYSQL_USER} -p${MYSQL_PASSWORD} ${MYSQL_DATABASE}'
```
