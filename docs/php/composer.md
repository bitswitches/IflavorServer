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
