# Docker で Laravel 環境を構築するよー！

https://github.com/ucan-lab/docker-laravel
こちらをベースにしており、`make`コマンドを使えばそれはそれは便利に使えるのじゃ～！

※make コマンドは GNU のコマンドなので、Windows には搭載されてません。  
そのため`choco install make`などでインストールする必要があるのです！

# チュートリアル開始

以下のリンクから始まる、チュートリアルをやっていく。
https://www.hypertextcandy.com/laravel-tutorial-todo-app-list-folders/

ここで、後で網羅すべき箇所を先にあげておく。

- Docker の構成
- 外部の Postgres サーバーに接続する方法を調べる
- 本番環境にデプロイする方法
-

## 初手

### コントローラを作成する

`php artisan make:controller TaskController`
このように、

`php artisan`は基本的なコマンド…

`php artisan list`で一通りのコマンドを眺めてみるとよい！

代表的なコマンドとしては…

- `serve`: サーバーを立てる
- ルーティング系
  - `php artisan route:list`: 設定されているルートを一覧表示
- DB 系
  - `php artisan make:model Admin`: Admin のモデルを作成
  - `php artisan make:migrate create_admins_table --create=admins`: マイグレーションファイルの作成
  - `php artisan migrate`: マイグレーションの実行
  - `php artisan make:seeder AdminTableSeeder`: Seeder ファイルの作成
  - `php artisan db:seed`: シードの作成
- `php artisan make:controller HogeController`: Controller の作成
- `php artisan tinker`: 対話コンソール起動

※参考記事: [Laravel artisan コマンドメモ / Qiita](https://qiita.com/zaburo/items/37768b743ed6d0e28bf5)

#### エラー発生

```bash
The stream or file "/work/backend/storage/logs/laravel.log" could not be opened in append mode: Failed to open stream: Permission denied
```

以下の記事に書いてあるコマンド 1 個で解決！
https://qiita.com/Usuyuki/items/b235a23d516a8d6dedc6
