# SSH接続および操作方法

具体的な接続方法は，[pdf資料](./SSH_connection.pdf)を確認してください．
## VSCodeを用いた接続
VSCodeの「Extensions」から「Remote-SSH」をダウンロードする．<br>
VSCodeのタブ上の「Remote Explore」からSSHの「+」をクリックしssh接続する．

ssh接続ができたら，`bash`を起動する．
```
$ bash
```

## SSHサーバーへのファイルの送信
クライアントPC側において，サーバーへユーザー名を指定し，ファイルを送信する．
```
# ファイルの送信
$ scp -r <file name> <user name>@<ip address>:<server-side file destination path>
```
例1. ファイル`test.txt`をipアドレス`192.168.xx.xx`のサーバー（アカウント名`exp1-gakusei`）の`/mnt/Data/Lab`に送信したい場合．
```
$ scp test.txt exp1-gakusei@192.168.xx.xx:/mnt/Data/Lab
```

例2. ディレクトリ`test`をipアドレス`192.168.xx.xx`のサーバー（アカウント名`exp1-gakusei`）の`/mnt/Data/Lab`に送信したい場合．
```
$ scp -r test exp1-gakusei@192.168.xx.xx:/mnt/Data/Lab
```

----
[Readme](../README.md)