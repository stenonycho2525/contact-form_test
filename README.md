# COACHTECH お問い合わせフォーム

ユーザがお問い合わせを送信できるフォームです。

## 作成者

小谷　知代

## 使用技術

- PHP 8.3.6
- Laravel 10.50.2
- MySQL 8.0
- Docker / Laravel Sail

## ER図

```mermaid
erDiagram
   
```

## 開発環境URL

http://localhost/

## 動作環境

PHP 8.3.6
Laravel Framework 10.50.2
Docker version 29.3.1
MySQL 8.4.9

## 環境構築手順

1. **リポジトリをクローン**

   ```bash
   git clone https://github.com/stenonycho2525/QAform.git
   ```

2. **.envファイルの準備**

   .env.example をコピーして .env を作成
   ```bash
   cd QAform
   cp .env.example .env
   ```

3. **Composer依存パッケージのインストール**

   dockerにComposer依存パッケージをインストール
   ```bash
   docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    -e COMPOSER_CACHE_DIR=/tmp/composer_cache \
    laravelsail/php82-composer:latest \
    composer install
   ```

4. **Laravel Sailの起動**

   Laravel Sailを起動する
   ```bash
   ./vendor/bin/sail up -d
   ```

5. **アプリケーションキーの生成**

   アプリケーションキーを生成
   ```bash
   ./vendor/bin/sail artisan key:generate
   ```

6. **データベースのマイグレーションを作成**

   マイグレーションを作成
   ```bash
   ./vendor/bin/sail artisan migrate
   ```

7. **フロントエンドのビルド**

   JavaScriptのパッケージをインストールする
   ```bash
   ./vendor/bin/sail npm install
   ```

8. **アプリケーションへのアクセス**

   ブラウザで以下のURLを開く
   http://localhost

## 機能一覧

- 名前、メールアドレス、電話番号を入力し、お問い合わせ内容を記入してユーザが問い合わせを送信することができます。
- ユーザ登録、管理画面へのログイン、ログアウトができます。