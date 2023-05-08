# Gitea

Gitea は、Git のリモートサーバーです。
[こちら](https://git.soine.site) から利用できます。

## push / clone 等に SSH を利用する

最も推奨される利用方法です。以下のように設定します。  
事前に `cloudflared` をインストールしておいてください。

1. `~/.ssh/config` に以下を追記する。

    ```
    Host git.soine.site
    HostName git-ssh.soine.site
    ProxyCommand cloudflared access ssh --hostname git-ssh.soine.site
    ```

2. 以下のコマンドを使用して、接続を確認する。

    ```shell
    ssh git@git.soine.site
    ```
    
    以下のような文言が表示されれば、設定に成功しています。

    ```
    PTY allocation request failed on channel 0
    Hi there, yude! You've successfully authenticated with the key named LDAP (soine.site)-SHA256:XEGJhmO6p0qu7C04gvtyJz5BHuIVUKOUIBqZDoSes0k, but Gitea does not provide shell access.
    If this is unexpected, please log in with password and setup Gitea under another user.
    Connection to git-ssh.soine.site closed.
    ```
