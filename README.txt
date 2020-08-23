HLSの使用方法

1.update & upgradeで最新まで上げておきます。

sudo apt update
sudo apt upgrade


2.nginxのレポジトリーを追加します。Officalじゃないので確認されるが[Enter]で進みます。

sudo add-apt-repository ppa:nginx/stable


3.rtspモジュールを追加します。

sudo apt install -y nginx libnginx-mod-rtmp


4.rtmpの設定をnginx.confの末尾に追加します。

sudo nano /etc/nginx/nginx.conf

ここのファイルに付属のnginx.confを追加


5.サービスリスタートします。

sudo service nginx restart


6.index.htmlにhtml5対応のビューワーのvideo-jsを追加します。

{ip}をサーバーIPに、{key}をストリームキーに置き換えてください。

sudo nano /var/www/html/index.html

ここに付属のindex.htmlを追加


7.配信にはOBSなどを使う

配信情報は以下のように設定します。

{ip}をサーバーIPに、{key}をストリームキーに置き換えてください。

配信先： rtmp://{ip}:1935/live
スリームキー： {key}


8.UI構築

付属のlive/index.htmlを追加

 先程のindex.html
            　　|--liveディレクトリ--|
            　　　　　　　　　　　　　index.html

あとはhttp://(IPアドレス)/live/にアクセスすると配信が表示されます。

これで配信サーバー構築完了です。お疲れ様でした。
