# Dockerを用いたRails開発環境作成テンプレート

## 1. Gemfileをローカルで用意
```
$ bundle init

# コメントアウトされている gem rails を有効に
$ vim Gemfile 
```

## 2. init.shを実行
init.sh は以下の処理を順番に実行する
1. コンテナを作成
2. Railsアプリケーション作成
3. database.ymlの差し替え
4. アプリケーション用のDB作成
```
./init.sh
```

## 3. docker-composeでコンテナ群を起動
```
docker-compose up
```

## Railsのバージョン指定
```
# Railsのバージョン一覧を確認
gem query -ra -n  "^rails$"

# Gemfileのrailsバージョンを固定
gem "rails", "X.X.X"
```

## 参考
- [How to cache bundle install with Docker](https://medium.com/magnetis-backstage/how-to-cache-bundle-install-with-docker-7bed453a5800)
