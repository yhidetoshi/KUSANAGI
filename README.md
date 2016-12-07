# KUSANAGI
![Alt Text](https://github.com/yhidetoshi/Pictures/raw/master/Kusanagi/kusanagi-icon.jpg)

- 環境
  - AWS
  - KUSANAGI: 8.0.1
  - OS: CentOS Linux release 7.2.1511
     - KUSANAGIのAMIからインストール
  
  
#### KUSANAGIコマンドについて
|コマンド    |内容         |
|:-----------|:------------|
|kusanagi status|kusanagiで管理しているモジュールの状態確認|
|kusanagi restart|kusanagiで管理しているモジュールの再起動|
|kusanagi bcache on |bcacheを有効にする|
|kusanagi fcache on |fcacheを有効にする|


- `$ kusanagi status`のコマンドを実行
  - 出力結果

- kusanagiコマンドではなく、systemctlコマンドでnginxを起動した場合、Nginxのログが出力されてなかった。
  - kusanagiコマンドで起動する必要がある
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

- bcacheを有効にする方法
   - `wp-config.php`に `define(‘WP_CACHE’, true);` を追加
      - (参考)cacheを有効にする 参考（https://japan3d.net/web/kusanagi_php7_mysql_connect_bcache/）
　 
- `# kusanagi bcache on`
- `# kusanagi fcache on`

