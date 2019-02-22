# laravel-docker

[![Build Status](https://travis-ci.org/Kento75/laravel-docker.svg?branch=master)](https://travis-ci.org/Kento75/laravel-docker)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

### クイックセットアップ

```
# PHP のみ
$ export DOCKER_BUILDKIT=1
$ docker-compose build
```

```
# 全部
$ docker-compose up -d
$ docker-compose ps
```

### Docker Laravel コマンド一覧

```
# Laravelアプリ作成
# ※ 前もって /src/public は削除しておく
$ docker-compose exec php laravel new sample
```

```
# 認証キー作成
$ docker-compose exec php php /src/artisan key:generate

# マイグレーション
$ docker-compose exec php php /src/artisan migrate

# コントローラ等の作成
docker-compose exec php php artisan make:XXXX XXXXXXXX

# PHPUnitの実行
docker-compose exec php ./vendor/bin/phpunit --testdox
```

Nginxの参照ファイル、ディレクトリ変更

```
# <プロジェクトルート>/nginx/default.conf

root /src/public;  # ディレクトリ
　　・
　　・
index index.php index.html;  # 参照ファイル
```
