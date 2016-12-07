# KUSANAGI
wordpress


#### KUSANAGIコマンドについて
|コマンド    |内容         |
|:-----------|:------------|
|kusanagi status|kusanagiで管理しているモジュールの状態確認|
|kusanagi restart|kusanagiで管理しているモジュールの再起動|

- `$ kusanagi status`のコマンドを実行
  - 出力結果
```
*** nginx ***
● nginx.service - The NGINX HTTP and reverse proxy server
   Loaded: loaded (/usr/lib/systemd/system/nginx.service; enabled; vendor preset: disabled)
   Active: active (running) since 金 2016-11-11 16:48:58 JST; 37min ago

*** Apache2 ***
● httpd.service - The Apache HTTP Server
   Loaded: loaded (/usr/lib/systemd/system/httpd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)

*** HHVM ***
● hhvm.service - HHVM virtual machine, runtime, and JIT for the PHP language
   Loaded: loaded (/etc/systemd/system/hhvm.service; disabled; vendor preset: disabled)
   Active: inactive (dead)

*** php-fpm ***
● php-fpm.service - The PHP FastCGI Process Manager
   Loaded: loaded (/usr/lib/systemd/system/php-fpm.service; disabled; vendor preset: disabled)
   Active: inactive (dead)

*** php7-fpm ***
● php7-fpm.service - The PHP FastCGI Process Manager
   Loaded: loaded (/usr/lib/systemd/system/php7-fpm.service; enabled; vendor preset: disabled)
   Active: active (running) since 金 2016-11-11 16:48:58 JST; 37min ago

*** Cache Status ***

fcache on
bcache off
完了しました

```
