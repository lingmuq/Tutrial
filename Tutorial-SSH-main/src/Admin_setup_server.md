# Setup of SSH server
## SSHサーバーの構築

はじめに，管理者ユーザー`exp1`で下記の操作を行う．

### 1. サーバー上で学生用ユーザーを作成．<br>

ユーザー名`exp1-gakusei`を作成する．
```
$ sudo useradd exp1-gakusei
$ sudo passwd exp1-gakusei
```
作成したユーザーのホームディレクトリを作成する．
```
$ cd /home
$ sudo mkdir ./exp1-gakusei
```
ここで，アクセス権限を確認する．
```
$ ls -l
# ファイル権限 所有権　所有者 ハードリンク数 グループ 更新日時 ファイル名
```
ファイル権限は，「所有権，グループ，その他ユーザー」の順で表す．
| アクセス権限 | 数字 | 記号 |
| ---- | ---- | ---- |
| 読み込み権限 | 4 | r |
| 書き込み権限 | 2 | w |
| 実行権限 | 1 | x |

今回は，誰でもディレクトリ`exp1-gakusei`にアクセスできるように権限を与える．
```
$ sudo chmod 757 exp1-gakusei
```

### 2. グループの作成<br>
ユーザー`exp1-gakusei`には管理者権限を与えたくない．
そこで，グループ`lab`を作成し，管理者権限をなしにアクセス権限を与える．
```
$ sudo groupadd lab
# 管理者ユーザー exp1 をグループ lab に追加する．
$ sudo usermod -aG lab exp1
# ユーザー exp1-gakusei の主グループを lab に変更する．
$ sudo usermod -g lab exp1-gakusei
```

ユーザー`exp1-gakusei`の所属グループを確認する．
```
$ groups exp1-gakusei
```

作成したグループ`lab`に所属するメンバーを確認する．
```
$ cat /etc/group
```

### 3. 学生用の作業ディレクトリ`/mnt/Data/Lab`を作成する<br>
学生ユーザー`exp1-gakusei`には，ディレクトリ`Lab`以外のアクセス権限は与えたくない．<br>
はじめに，ディレクトリ`/mnt/Data`をグループ`lab`と紐付けて，アクセス権限を変更する．<br>
```
$ cd /mnt/
$ sudo chgrp lab Data
$ chmod 750 Data
```
次に，ディレクトリ`/mnt/Data/Lab`を作成する．
```
$ cd Data
$ mkdir Lab
```
同様に，ディレクトリ`Lab`もグループ`lab`と紐付ける．
```
$ sudo chgrp lab Lab
```

### 4. ベンチマーク等ディレクトリ`/mnt/Dataset`を作成する<br>
ベンチマーク保存用ディレクトリ`Dataset`を作成する．<br>
```
$ cd /mnt
$ mkdir Dataset
```
ディレクトリ`/mnt/Dataset`をグループ`lab`と紐付けて，アクセス権限を変更する．<br>
ここでベンチマークディレクトリ'Dataset'は，学生ユーザー`exp1-gakusei`に書き込み権限は与えない．
```
$ sudo chgrp -R lab Dataset
$ chmod -R 755 Dataset
```

## クライアントからのSSH接続 (CUIでの操作のみ)
これはCUI操作のみのTerminalからssh接続する方法である．<br>
VSCodeを利用した操作は，別ページで紹介する，<br>

クライアント側からssh接続するには，ユーザー名とipアドレスが必要である．
```
$ ssh <user name>@<ip address>
```

*Note* : もしOSを再インストールしてipのみ同じで中身が異なると下記のようなエラーがでる．
```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ED25519 key sent by the remote host is
SHA256:EOFUrfmwxOs899RT4znpQfkciHRlWQkIfZr10m+bB3E.
Please contact your system administrator.
Add correct host key in /home/hotta/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in /home/hotta/.ssh/known_hosts:14
  remove with:
  ssh-keygen -f "/home/hotta/.ssh/known_hosts" -R "192.168.43.54"
Host key for 192.168.43.54 has changed and you have requested strict checking.
Host key verification failed.
```
この場合，次のコマンドを入力する．
```
$ ssh-keygen -R <ip address>
```

## クライアントからのSSH接続切断 (CUIでの操作のみ)
はじめに`bash`を閉じる．
```
$ exit
```
次に，ssh接続を切断する．
```
$ exit
```

----
[Readme](Admin_Readme.md)