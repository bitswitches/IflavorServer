# PHP

## phpenv
- install phpenv (if you want develop in local)

- brew install openssl libxml2 jpeg libmcrypt

- phpenv install 7.1.11
- if below error occur, type `LDFLAGS="-L/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/lib/system" phpenv install 7.1.11`
```
  ld: file not found: /usr/lib/system/libsystem_darwin.dylib for architecture x86_64
  clang: error: linker command failed with exit code 1 (use -v to see invocation)
  make: *** [ext/opcache/opcache.la] Error 1
```
  

## Note
### [php 7.1のインストール](https://qiita.com/chidakiyo/items/3b81a442dda34d439b42)
- rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
### 対話型シェルの起動
- php -a 
### [php のインストールしたパッケージリストの表示](https://stackoverflow.com/questions/478844/how-do-i-see-the-extensions-loaded-by-php)
- php -r 'print_r(get_loaded_extensions());'
- php -m
- php -i


## Pakcage Manager
- composer
