# 4. リポジトリの作成・管理

GitHubでは新しいリポジトリを作成することで，プロジェクトを管理することが可能である．
GitHubによるプロジェクト管理は，リモートでのプロジェクトの遂行を容易にするだけでなく，プログラムの変更履歴を参照することもできる．
そこで，本ページでは[**リポジトリの作成**](#リポジトリの作成)と[**リポジトリの管理**](#リポジトリの管理)を紹介する．

## リポジトリの作成
GitHubにおけるユーザーページから「Your repositories」をクリックし，下図に示す「New」をクリック．<br>
<left>
<img src="https://dsm01pap004files.storage.live.com/y4mZ9qWqN_ZFaKa_k5tuOullZRnMW-gNyJRP3a0_8gp9KQXys17Pln4O8tzSj_2gUnioACoCeuv065SW9c8GqEIiH0t3_Xrt1ZmTacrokG0DNaj-O7MFXys3Cbt-gEDEybSjiJwa0fd1M9xT5-3c7jNfkliYsY0ptarS14mX7_jhayhR7CTqPo3VIMEcWhLdlfF?width=2237&height=470&cropmode=none" width=50%>
</left>

「Repository name」に任意のプロジェクト名を入力し，「Add a README file」に✓を入れる．<br>
<left>
<img src="https://dsm01pap004files.storage.live.com/y4mL3HPkHwf3HwGkER39QqNzAHAk8fzGDeYmqXSsnmkroMdqmlEqZxh7PA1nQskFt0MIv-usiLWBeKTwujqyyVeGgOjyTbrB3sW7Gg3SzfnAKiOtlc761VZm-4K4b-FNar-5NLKmFY6iSa4l__rRQb18mgzPJfMWAHAZQ8X87GNHvvIkGb5qEZDSjE3x7BPZb-8?width=2159&height=2013&cropmode=none" width=50%>
</left>
<br>
次に「Create repository」をクリックすることでリポジトリを作成できる．
<left>
<img src="https://dsm01pap004files.storage.live.com/y4mj5D8Ui-EhOiToeSxTgvi9c0L1oi6BhMf8Iq8bUdy9M_o55ASjo-E9eS26-yl4QXZRvQrx5opi6DJA-DwLFTwKc4DBRCs2lZADb1DcBQDeArxNEnuJ87_nZrtyEEhbMvsdA5rnXLfFE2UkMU-6Tl6uYgLDVJhBz59AgHwthpNYcPUFoR-aNQQV7pXtvegWhmS?width=980&height=422&cropmode=none" width=50%>
</left>

## リポジトリの管理
クライアント側（ユーザー）でリポジトリを管理するために，SSH接続によるプロジェクトのクローンを作成する．<br>
1. プロジェクトのクローン作成<br>
    リポジトリのプロジェクトページにおいて，下図に示すCode->SSHから「SSH URL」をコピーする．<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mncuxkK7qsOSPcNdhpKI4_hRH_1vz5WDCQnD85CzthKcqAP3yYIBStbHuselZJe1XaKGGSg1JgOh0iXSCblpwyc9dHZpF_HMDDAoFqRjcraCw5fZNSFsPkBuoeOzC3Yf03unKY1jsCWo9oi5oFuiQYJGCvdC1w47exbOHtm5s71vbqjkdSPpNKjbxxHUQv4wN?width=2513&height=1549&cropmode=none" width=50%>
    </left>
    <br>
    次に，Windowsの場合はMinGW64，Ubuntuの場合はterminalから，ローカルリポジトリを作成したい場所に次のコマンドを入力する．
    ```
    $ cd <ポジトリを作成したい場所>
    $ git clone <コピーしたSSH URL: e.g., git@github.com:team-Kwork/Tutorial-Git.git>
    ```
2. リモートリポジトリの管理
    先ほど作成したローカルリポジトリにおいて変更した箇所をローカルリポジトリに反映する．<br>
    まず，ローカルリポジトリにおけるルートディレクトリから次のコマンドを入力して変更箇所を確認する．
    ```
    $ git status
    ```
    変更箇所をステージングエリアに追加し，変更箇所に関するコメントを残すために次のコマンドを入力する．
    ```
    $ git add -A
    $ git commit -m "任意のコメント:e.g., Fixed the code for $ loading datasets."
    ```
    最後に，変更箇所をローカルリポジトリに反映するために，次のコマンドを入力する．
    ```
    $ git push
    ```

<br>

***
[ホーム](../Readme.md)