# 接続方法

アカウント作成を管理者 (yude) に申請してください。

## 接続

### 共通

* サーバー アドレス: `gate.soine.site`
    * IPv4 のみ: `gate4.soine.site`
    * IPv6 のみ: `gate6.soine.site`

### SoftEther VPN (推奨)

* ポート: `443`, `5555` (推奨)
* 仮想 HUB: `DEFAULT`
* 接続が不安定な場合、「NAT-T 無効」にチェックを入れてください。

### OpenVPN

* ポート: `443`, `5555`, `1194`
* [OpenVPN プロファイル](./soinet.ovpn)

### L2TP over IPsec / EtherIP over IPsec

* ポート: 標準 (`500/udp`, `4500/udp`, `esp`)
* 事前共有鍵: `soinet`
* ISAKMP Phase 1 Key: 管理者までご連絡ください。

## 設定

* IPv4
    * アドレス範囲: `172.20.0.0/22` を使用します。他のソフトウェア等と競合しないように設定してください。
    * DHCP を有効にすると、自動的に IP アドレスが付与されます。
* DNS
    * DHCP によって自動的に設定されるはずです。
    * 手動で設定することもできます (DNS サーバー: `172.20.0.2`)。
* 設定例: SoftEther VPN Client + systemd-networkd + systemd-resolved
    * `/etc/systemd/network/vpn_vpn.network`
        ```
        [Match]
        Name = vpn_vpn

        [Network]
        Domains = ~soinet
        DHCP = v4
        IPv6AcceptRA = true
        DNS=172.20.0.2

        [Route]
        Destination=172.20.0.0/22
        ```
