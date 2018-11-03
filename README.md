# 開発環境

## 必要環境

* Git
* Docker

## リポジトリのクローン

```
$ git clone git@github.com:Ushinji/rails_on_docker.git
$ cd path/to/repo
```


## 起動手順

イメージのビルド

```
docker-compose 
```

Gemインストール

```
docker-compose exec --rm app bundle install
```

database.ymlのコピー

```
docker-compose run --rm app cp template/database.yml config/database.yml
```

DBマイグレーション

```
docker-compose exec --rm app bundle exec rails db:create

docker-compose exec --rm app bundle exec rails db:migrate
```

コンテナー起動

```
docker-compose up -d
```

http://localhost:3000 にアクセスして、アプリが表示されることを確認。

