## 実装環境
```
nginx
PHP
node(ベースイメージ ubuntu)
```

## 初回 環境構築(例) React & Laravel 

--React 構築方法--
```
# Docker 起動
docker-compose up -d

# frontコンテナに入る
docker-compose exec front bash

# Reactプロジェクト作成
npx create-react-app /var/www/html/app

# プロジェクトの中身を移動
mv -if /var/www/html/app/* /var/www/html/
mv -if /var/www/html/app/.[^\.]* /var/www/html/

# 空になったディレクトリ削除
rm -rf /var/www/html/app

# React Build
npm run build

# React 開発用サーバー起動
npm run start

# 起動確認 ポート番号はdocker-compose.ymlを参照
http://localhost:xxxx/
```

<br>

--Laravel 構築方法--
```
# backコンテナに入る
docker-compose exec back bash

# Laravelプロジェクト作成
composer create-project "laravel/laravel=8.*" /var/www/html/laravel_app

# プロジェクトの中身を移動
mv -if /var/www/html/laravel_app/* /var/www/html/
mv -if /var/www/html/laravel_app/.[^\.]* /var/www/html/

# 空になったディレクトリ削除
rm -rf /var/www/html/laravel_app
```

-- nginx --
```
# 起動確認 ポート番号はdocker-compose.ymlを参照
http://localhost:xxxx/
```


## -- 本番デプロイ用(ローカルでの開発時は利用しない) --
docker-compose-prod.yml  
Dockerfile.prod
```
# 本番用 Docker 起動
docker-compose -f docker-compose-prod.yml up -d
```