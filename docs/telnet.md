# Telnet

Telnet を用いてサーバーに接続して、 Web ページの公開やパスワードの変更などを行えます。(非推奨)

### `cloudflared` を使用して接続する

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

2. パケットをプロキシするために、`cloudflared` を使用します。
    ```
    cloudflared access tcp --url localhost:2323 --hostname telnet.soine.site
    ```

3. 以下のコマンドを実行して、サーバーに接続します。

    ```shell
    telnet -l ユーザー名 127.1 2323
    ```

    * 初回ログイン後は、`passwd` コマンドを使用して初期パスワードと異なるパスワードに変更してください。

### Tailscale を使用して接続する

1. Tailscale をインストールします。

    [Download ・ Tailscale](https://tailscale.com/download) を参照してください。

2. 以下のコマンドを実行して、サーバーに接続します。

    ```shell
    telnet -l ユーザー名 soine.soine.site.beta.tailscale.net
    ```

    * 初回ログイン後は、`passwd` コマンドを使用して初期パスワードと異なるパスワードに変更してください。
