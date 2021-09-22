# ユーザ認証にActive Directoryを利用するLaravel Breezeサンプル
## 説明
LdapRecordを利用してLaravel Breezeのユーザ認証にWindows ServerのAD認証を使うサンプルです。
https://ldaprecord.com

### 使い方
```
git clone このレポジトリ
cd クローンしたレポジトリ名
cp .env.example .env
composer install
php artisan key:generate

vi .env
---下記を実環境に合わせて修正---
DB_CONNECTION=mysql or pgsql or sqlite

LDAP_LOGGING=true
LDAP_CONNECTION=default
LDAP_HOST=127.0.0.1
LDAP_USERNAME="administrator@yourdomain.local"
LDAP_PASSWORD=secret
LDAP_PORT=389
LDAP_BASE_DN="dc=local,dc=com"
LDAP_TIMEOUT=5
LDAP_SSL=false
LDAP_TLS=false
---------------------------

php artisan migrate

LDAPの接続テスト
php artisan ldap:test

サーバの稼働
php artisan serve
```
http://localhost:8000

上記URLにアクセスし、ログインから自分のADアカウントでログインします。
