# SOINET
yude.jp / soine.site が提供する閉域網

## 接続方法
アカウントについては、他のサービスと共有していません。  
アカウント作成を管理者 (yude) に申請してください。
### 接続
#### 共通
* サーバー アドレス: `gate.soine.site`
#### SoftEther VPN
* ポート: `443`
#### L2TP over IPsec
* ポート: 標準 (`500/udp`, `4500/udp`, `esp`)
* 事前共有鍵: `soinet`
#### OpenVPN
* 管理者まで連絡してください。
### 設定
* IPv4 アドレス レンジ: `172.20.0.0/22` を使用します。他のソフトウェア等と競合しないように設定してください。
* IPv4: DHCP を有効にすると、自動的に IP アドレスが付与されます。
* DNS: DHCP によって自動的に設定されるはずです。手動で設定することもできます (DNS サーバー: `172.20.0.2`)。

## 稼働中のサービス
|  ドメイン  |  プロトコル  |  説明  |
| ---- | ---- | ---- |
|  `www.soinet`  |  http (`80/tcp`)  |  挨拶  |
|  `pbx.soinet`  |  chan_pjsip (`5060/udp`, `5060/tcp`)  |  IP 電話  |
|  `pipe.soinet`  |  http (`80/tcp`)  |  Piping Server  |
|  `ns.soinet`  |  dns (`53/udp`)  |  DNS  |
|  `ddns.soinet`  |  dns (`53/udp`), http (`80/tcp`)  |  ダイナミック DNS  |
