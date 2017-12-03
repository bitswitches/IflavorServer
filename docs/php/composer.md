# Composer

- `curl -sS https://getcomposer.org/installer | php` in your project dir
- write dependencies in `composer.json`
  - require
  - require-dev
- manual
  - `php composer.phar install`
    - options `--no-dev` to avoid install development dependencies.
  - `php composer.phar update`
    - options `--no-dev` to avoid install development dependencies.

## Composerのcreate-projectが何をやっているのか調べてみた
結論は対象パッケージをgit cloneしてからcomposer intsallするのとほぼ同じである。
- [参考](https://qiita.com/DQNEO/items/74f4bb8fe447e4582a97)

## 後で読む
- https://niconare.nicovideo.jp/watch/kn1371
- https://qiita.com/tadsan/items/86099d44d12f1103b0a0
- https://qiita.com/yotasasaki/items/cc1a4936c0c92099db5a
- https://packagist.org/
- https://getcomposer.org/doc/04-schema.md#autoload-dev
- https://akamist.com/blog/archives/395
- https://getcomposer.org/doc/01-basic-usage.md#commit-your-composer-lock-file-to-version-control
- https://qiita.com/notona/items/c5a087d8dd446d315e6e
- https://qiita.com/kd9951/items/14cddc050745185011ee
- https://getcomposer.org/doc/04-schema.md#require-dev

