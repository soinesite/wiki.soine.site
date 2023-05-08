# 接続方法
アカウントについては、他のサービスと共有していません。  
アカウント作成を管理者 (yude) に申請してください。
## 接続
### 共通
* サーバー アドレス: `gate.soine.site`
### SoftEther VPN
* ポート: `443`, `5555` (推奨)
* 仮想 HUB: `DEFAULT`
### L2TP over IPsec / EtherIP over IPsec
* ポート: 標準 (`500/udp`, `4500/udp`, `esp`)
* 事前共有鍵: `soinet`
* ISAKMP Phase 1 Key: 管理者までご連絡ください。
### OpenVPN
* [OpenVPN プロファイル](./soinet.ovpn)
## 設定
* IPv4 アドレス レンジ: `172.20.0.0/22` を使用します。他のソフトウェア等と競合しないように設定してください。
* IPv4: DHCP を有効にすると、自動的に IP アドレスが付与されます。
* DNS: DHCP によって自動的に設定されるはずです。手動で設定することもできます (DNS サーバー: `172.20.0.2`)。
