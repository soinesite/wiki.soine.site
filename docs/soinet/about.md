# SOINET について

yude.jp / soine.site が提供する閉域網

## 稼働中のサービス

|  ドメイン  |  プロトコル  |  説明  |
| ---- | ---- | ---- |
|  `www.soinet`  |  http (`80/tcp`)  |  挨拶  |
|  `pbx.soinet`  |  chan_pjsip (`5060/udp`, `5060/tcp`)  |  IP 電話  |
|  `pipe.soinet`  |  http (`80/tcp`)  |  Piping Server  |
|  `ns.soinet`  |  dns (`53/udp`)  |  DNS  |
|  `ddns.soinet`  |  dns (`53/udp`), http (`80/tcp`)  |  ダイナミック DNS  |
|  `proxy.soinet`  |  http<br>(標準: `8080/tcp`, JavaScript なし: `8081/tcp`, CSS なし: `8082/tcp`, JavaScript & CSS なし: `8083/tcp`)  | retro-proxy, http プロキシ |
|  `sdr.soinet`  |  rtl_tcp (`1234/tcp`)  |  rtl_tcp, ソフトウェア無線 |
|  `smb.soinet`  |  samba (`137/udp`, `138/udp`, `139/tcp`, `445/tcp`)  |  Samba, ファイル共有  |
|  `ftp.soinet`  |  ftp (`21/tcp`)  |  FTP, ファイル共有<br>ユーザー名: `user`<br>パスワード: `user`  |
| `speed.soinet` | iperf3 (`5201/tcp`) | iperf3, スピードテスト |
