# Web ページのホスティング
SSH でサーバーに接続し、ホームディレクトリに存在する `public_html` にコンテンツを配置すると、以下の URL のもと公開されます。  

* URL: `https://soine.site/~アカウント名`

サブドメインの利用を希望する場合は、[管理者](mailto:yude@soine.site) まで問い合わせてください。 
## スペック
* Web サーバー: nginx
    * セキュリティ対策のため、シンボリックリンクは使えません。
* バックエンド: PHP (php-fpm)
    * バージョン: 8
    * Zend Engine
