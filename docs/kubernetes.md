# Kubernetes

共用 Kubernetes クラスタ

## ストレージ

* StorageClass として [Longhorn](https://longhorn.io/) がインストールされており、既定でこれが使われます。

## 制約

* 単一の namespace が消費できる RAM には、合計 2 GiB のハード リミットがあります。
* 単一の namespace が要求できるストレージには、合計 50 Gi のハード リミットがあります。

## HTTP / HTTPS サービスの公開

* `*.soine.site` 以下において Web サービスを公開できます

### Ingress の作成

あなたの namespace 内にある `foo` という Service を、`bar.soine.site` で公開したいとして、以下に例を示します。
なお、それぞれの Service は、http の場合 80/tcp ポートを、https の場合 443/tcp ポートを expose しているものとします。

* http サービスの場合

    ```
    kubectl -n bar \
    create ingress bar.soine.site \
    --rule="bar.soine.site/*=foo:80"\
    --class cloudflare-tunnel
    ```

* https サービスの場合

    ```
    kubectl -n bar \
    create ingress bar.soine.site \
    --rule="bar.soine.site/*=foo:443"\
    --class cloudflare-tunnel \
    --annotation "cloudflare-tunnel-ingress-controller.strrl.dev/backend-protocol=https" \
    --annotation "cloudflare-tunnel-ingress-controller.strrl.dev/proxy-ssl-verify=off"
    ```
