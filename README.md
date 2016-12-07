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



- kusanagiコマンドではなく、systemctlコマンドでnginxを起動した場合、Nginxのログが出力されてなかった。
  - kusanagiコマンドで起動する必要がある

- bcacheを有効にする方法
   - `wp-config.php`に `define(‘WP_CACHE’, true);` を追加
      - (参考)cacheを有効にする 参考（https://japan3d.net/web/kusanagi_php7_mysql_connect_bcache/）
　 
- `# kusanagi bcache on`
- `# kusanagi fcache on`


### KUSANAGIインストール後のケア

#### WordPress管理画面の接続制限

- WordPress管理画面のIP制限 80/443ポート　(アクセスできるクライアントをIPで制限する)
 - /etc/nginx/conf.d/wordpress_http.conf
 - wordpress_ssl.conf
``` 
location ~* /wp-login\.php|/wp-admin/((?!admin-ajax\.php).)*$ {

                satisfy any;
                allow <IP-Address>/32;
                allow <IP-Address>/29;
                allow 127.0.0.1;
                deny all;
                #auth_basic "basic authentication";
                #auth_basic_user_file  "/home/kusanagi/.htpasswd";

```

#### Pingback攻撃対策
- DocumentRoot/wp-content/thems/配下で使っているthemsのfunctions.phpに下記の１行を追加する。
```
add_filter('xmlrpc_enabled', '__return_false');
```
