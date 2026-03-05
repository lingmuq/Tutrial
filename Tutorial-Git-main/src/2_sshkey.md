# 2. GitHubにおけるSSH接続の設定

GitHubではSSHプロトコルを使うことで，任意のパソコンから自動的にGitHubサーバーに接続することが可能である．
SSHプロトコルは，SSHキー（秘密鍵と公開鍵）を作成することでクライアント側（ユーザー）とサーバー側（GitHub）での安全な接続を確立している．
そこで，本ページでは[**新しいSSHキーの作成方法**](#新しいsshキーの作成方法)と[**GitHubへのSSHキーの追加方法**](#githubへのsshキーの追加方法)を紹介する．

## 新しいSSHキーの作成方法
1. **公開鍵・秘密鍵の生成**<br>
    次のコマンドをターミナル上で実行する．
    ```
    $ ssh-keygen -t ed25519
    ```

    Note: 上記のコマンドが実行できない場合には，次のコマンドをターミナル上で実行する．
    ```
    $ ssh-keygen -t rsa
    ```
    次に，<br>
    `> Enter a file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter]`<br>
    上記の表示に対して`Enter`キーを押すことで，SSHキーをデフォルトパスに保存する．

2. **公開鍵ファイル「~/.ssh/id_rsa.pub」のコピー**<br>
    次のコマンドをターミナル上に入力することで公開鍵をコピーできる．<br>
    【Windows】
    ```
    $ clip < ~/.ssh/id_ed25519.pub
    ```
    【Ubuntu】
    ```
    $ xclip ~/.ssh/id_ed25519.pub
    ```

## GitHubへのSSHキーの追加方法
1. **GitHubにおける公開鍵の設定**<br>
    GitHubにおける任意のページで，右上にあるプロファイル画像をクリックし，「Settings」から「SSH and GPG keys」をクリック．<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mUUiwbjYXpp4fShYEKBCefZnSK3ZwcGgsjhw_ECq1WjekVYze_cpZe8nWWWizVmUOMQnddDTP8t3_NAZRbJF2eyKWN8kKZJbsO1I-7KrMiTdA467Huf23Ref846g0LpgW2KOU2ZohuDM0oNSnr3UCyZyuns4zM7xU99Lkmgw_0ySj0fXPm7n3hbOtDZe0wmdI?width=360&height=576&cropmode=none" width=30%>
    </left><br>
    SSHキーを生成するファイルと，パスワード，パスワードの確認を3回聞かれるが，<font color="Red">3回「Enter」をクリックすれば良い．</font>．<br>

    次に，画面右上の「New SSH key」をクリック．<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4m9YG11uUWadkkrba7dOkgf0ihQ-p2u7yi0OWghIuxf5Sv4bLmGcTG-SFJrARhqujCRZ1ynLAaGsBhJ99qnCzZ8_sbqiK8ISLu5xuTv4ix1EqxZ2egwE2rAF0YO0MTsjcvnVNYlZ1Xl8k3tN8gipQ-6LC6Lt7r7meh2OTNQYeSm3thqn4S-xkWh-nrQSWjXMa_?width=757&height=100&cropmode=none" width=70%>
    </left><br>
2. **公開鍵のGitHubへの追加**<br>
    「title」に任意の公開鍵名（例えば，研究室PC）を記入．<br>
    「key」に"[新しいSSHキーの作成方法](#新しいsshキーの作成方法)"でコピーした公開鍵を貼り付ける．<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mX8UpVZYkJoq7cz47Dx1LLVr1vsPZTeKg0-5FHvC0_r9ZadwbLVfW6UPm13PpNHvuvOjJuTLRgNxrhB7wYEmMxrPtzukO3h3vY1BbdjXbd1Ibjk8jMe1wYsn6flcMOk4WAldBFe8a5KfqJYBzjLRVPZ3GreE6nGw-mKsq4v_M5Zsl4FB1XsDJbTxSvBya7JGn?width=774&height=428&cropmode=none" width=50%>
    </left><br>
    最後に，「Add SSH key」をクリックすることでGitHubにおけるSSH接続の設定は完了．<br>

<br>

***
[ホーム](../Readme.md)