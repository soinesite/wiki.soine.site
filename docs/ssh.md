# SSH

SSH を用いてサーバーに接続して、 Web ページの公開やパスワードの変更などを行えます。

## 接続方法

`cloudflared` (Cloudflare Tunnel) を用いて接続します。

1. `cloudflared` コマンドをインストールします。
    * [こちら](https://pkg.cloudflare.com/index.html) に公式のドキュメントがあります。
    * 主要なディストリビューション / OS では、以下のようにしてインストールできるでしょう。
        * macOS (Homebrew)

            ```shell
            brew install cloudflared
            ```
        
        * Arch Linux (pacman)

            ```shell
            sudo pacman -S cloudflared
            ```
        
        * FreeBSD (pkg)

            ```shell
            pkg install cloudflared
            ```

2. 以下の内容を `~/.ssh/config` に追記します。
    ```
    Host soine.site
        User ユーザー名
        HostName ssh.soine.site
        ProxyCommand cloudflared access ssh --hostname %h
    ```

3. 以下のコマンドを実行して、サーバーに接続します。

    ```shell
    ssh soine.site
    ```

    * ログイン後は、`passwd` コマンドを使用して初期パスワードと異なるパスワードに変更してください。
