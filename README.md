## 初回 環境構築
```
# docker build
docker-compose up -d

# Reactプロジェクト作成
npx create-react-app ./front/app
# プロジェクトの中身を移動
mv -if ./front/app/* ./front/
mv -if ./front/app/.[^\.]* ./front/
# 空になったディレクトリ削除
rm -rf "./front/app"

# frontコンテナに入る
docker-compose exec front bash

# React Build
npm run build

# ブラウザで起動確認
http://localhost:xxxx/


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