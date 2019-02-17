# laravel-docker

[![Build Status](https://travis-ci.org/Kento75/laravel-docker.svg?branch=master)](https://travis-ci.org/Kento75/laravel-docker)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

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

Laravelアプリ作成コマンド(例)

```
$ docker-compose exec php laravel new sample
```

Nginxの参照ファイル、ディレクトリ変更

```
# <プロジェクトルート>/nginx/default.conf

root /src;  # ディレクトリ
　　・
　　・
index index.php index.html;  # 参照ファイル
```
