# 1. Gitのインストール方法

Gitをインストールするためのチュートリアル
- [Windows](#windows)
- [Ubuntu](#ubuntu)

## Windows

1. GitHubのインストーラーを[ここ](https://gitforwindows.org/)からダウンロード<br>

2. ダウンロードした"Git-x.xx.x-64-bit.exe"を実行<br>

3. 基本的にデフォルトの状態で「Next」を押すだけでいい<br>
- インストール先の選択<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mYrEouiaxZRhTe9SU6Z8_y-k5tU0ba-HT0NXYsB7NRvbfYybnJvC8JkTQsqsbnIc_F3eKJJSYsC2uVz_iJGJHzNP4tAE3UiWm9f2pFrwY-netB5uSAShraoI47CBBaVFqS4t-JY_YyKH_vrP4Ojc44xCO42ESA10CpkA17g6AXChbDj0zHaOlqxLGXyUkbXds?width=499&height=392&cropmode=none" width=50%>
    </left>

- コンポーネントの選択<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mkKP-D0P1NL72eGyS81S52QZC0nkmvNYUL0Vbw869dgryELTcQeefkSqeG2sQq4IgSP6XZ02B0rbpqYP-Y5kLS123HxIGyQnusHHYjsBRBPyIhhEoWc7DKTAk7CgGDA2pJ3JFlEtpAjZMbE1DAN3KaT-yB4_h1znGLfRlYCN37h_QQAskjv8gGv1Fg2p5jts0?width=496&height=387&cropmode=none" width=50%>
    </left>

    Note: デスクトップにショートカットを作成したい場合は，「Additional icons」と「On the Desktop」にチェックをつける．
    また，右クリックのコンテキストメニューに「Git Bash」や「Git GUI」を追加したくない場合は，の「Windows Explorer Integration」のチェックを外す

- Windowsスタートメニューのフォルダ名<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4m8EUeytIspukCyA1-k3pdjh7T8qX18kcdq3P1dpt0xhzCAa2aqrzr93OItOAVwwrQUK5j2vgBcAiaelSdIW8oFc0PulJnKx9t3t_lfFnMgwSKQRpAsaST5qcXRMnj_JUXQj2L7klQW9w_I4C2LlBdJtp-WPf2JN7F7AnUN_0eA0V78wPhDYk0cZ9rmIEgWVtT?width=490&height=388&cropmode=none" width=50%>
    </left>

- エディタの選択<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mxmtwD7iFwoNZ1JyWco5iOCliJi6lvaPG3HEPliClBxxL1fW-iStWP19-NMBYT5riYI0E-cQNlhWJ5p0EmmZSM7tUiE6OnOHiXonVxYO7OVUOQjU8RvplyBFc1VytsxvYBEt0XQRNuikHBNBLiMImgazs6WgrIe_OQXQalybqWb9gPmriiU_-tqYvtg4EuziG?width=496&height=388&cropmode=none" width=50%>
    </left>

    Note: デフォルトエディタはvimになっている．特に変更しなくても問題ないが，今回はNotepad++を用いる．

- 新しいリポジトリの初期ブランチ名<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mEd7N8hgJe_OjuQ1Z-6m6ayXHvao8P23cNVSp8FKqjYdY8fdGys5h2WT8khaIpWBk_NOij1Py52ugXA_V_LlHm29_LV6Puye4-Z9cTit-5LLo-5ZhosJso2wX-KwxL2PIEtwMiCeLoY9TUq21eyHucYZIM3vIZ7nZXlOw0cXy3Lem3-s0NpUJfVMiV_fXRg3s?width=490&height=384&cropmode=none" width=50%>
    </left>

    Note: 「Let Git decide」は，初期ブランチ名に"master"という名前が適用される

- 環境変数の設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mnO3iRGs9lnSwc_ticGu1E7R2wFBzdcsDkKsiWGzG6qub_yR_eBtBwc8nkR3rnEhugD33pFRGJmUtyPq_QB7VQgCsQ2DWQm_HnmYzV2-_UF-W6DSHGa4QI9vucclR-tJml6Nw3G0ysuI8vvs6DkFdwPd-nFebJPECZDmNLdJr-ZGh1SQbQQzQa_-dr9r3vjT9?width=495&height=387&cropmode=none" width=50%>
    </left>

    Note: コマンドプロンプト等でもgitコマンドを使えるようにするために，「Git from the command line and also from 3rd-party software」を選択する

- SSH設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mWlCOctXCycWz3lteQPXhpD-zH2i5vunOh1CnHY00TZ3yL73s3jVExNuvGdThvP6yqvOTxKk34ecpdgxhnV3odhUo5PUDJ4T0Pi3_8XQzC7fKVzrBcw9IhGlQekb85i1OebhLL4GTqUaxsbhwsCllcZz_9MmEczwqdRMAOTfn9dJk03h0brTaXqXTn_0Y_lrL?width=491&height=386&cropmode=none" width=50%>
    </left>

- HTTPS設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4m4--JlaprDo3TW5plD9sLF7unVMuJ5mSuj35tjtlgDwBOsUca0LScc_SrcqB4lx9NcUs9cmcJ8Dl9bPMrDOucc4dIXz7Z7dkF_45b0MgMZMsFFWoHsuU_Qkql031nwhX1S_muBJd0ibj6KpiouSXcv4w7UNh0rAOwpayIelawVnjHNs70EHQw3k2k25Jg7YeH?width=489&height=387&cropmode=none" width=50%>
    </left>

- 改行設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mMgcJEscqoy0GE_HgWZmnLHJJsRauZgROPIQYH7xxF7A3YbLC0z_FEIiqhMl4XlaqBVhbCuSQ9lIhiDuNPfj7slv4qvvdAHSpAeqL5oogRxyFweoIs5cE2NPbDvAyrHkVa_iOss84WAIMwDuCDfoWOQ_krNPlgbBn3T45r-LNh1fTi6AlE3TER0sc0HgnZ8Lb?width=491&height=386&cropmode=none" width=50%>
    </left>

- Git Bashで用いるコンソールの設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mMpwZ7hsQfSPV2k-m2uzS4NrwFUKE7JL4KxHyDaMq4nBXJapm0unm-LwW3KDzG0gGAeYZcKVhNEy6ni8bFhWJiBe8NHKZ9K_siJLIOV4QuIa_izBHQukTVktHFDaaBH9dUtwo0m1ehV_4swzdDIvjj-QKq3KIlBUzXrNfumNZPZDr8Jshy40-SCXY7HJj9UCs?width=490&height=387&cropmode=none" width=50%>
    </left>

- 「git pull」での設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4m4mMXrlZfRU0pB6-SKLA-Bc-Zw7227_BZKCzPOetdv2z1_TJbxTqlhsTzqc03Rb7v9xDNhIzHqo9kpB6CFlxXTNGtKiBvxrM8p8tr9vTc33NBLagrHAtKRzuY6x_0z12Jr8SPLARkD0W6SX0cLJgTBM28hJlNsOuFTiP52JaEZcyWM2GMZEPT9ASxgY0P-sAp?width=491&height=387&cropmode=none" width=50%>
    </left>

- 認証補助設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mdwfOOjsrX9ucxfT2P_HQSn3UGuO6jMN1_uyGcYGYGGTThcDeSXvsZWs-4Obd2XTLvxPOltAGN7RWUR4buSk-1FY9LctLmeS1OZqMjZZEI3fVTXULgb2Kd-ExLFDlVbqWKJT0GN481Pj8VcvI7lL85PsObjeJoYoy63UmnWF3gtzIPgRAYjUtX1v8b2iuVKYI?width=488&height=389&cropmode=none" width=50%>
    </left>

- 追加オプション<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mOi1fD8-sCybzGB-aoAphDkcKYOH8QJUrcLrIGAzIgIy2JXypfM4hLq8yuPDTsGZEZaTf_nzNHwsjp3lPw0UP05osLKA5_iSFvGHZAOGI4OkmfdI-py3D3_DmIQFDNTCRSXxpWnB70oZKZUJJxyosmzE1ITK4sBg5Icjv8isKDYPRtL0N-IbJ8yq4K9BNYU1m?width=493&height=388&cropmode=none" width=50%>
    </left>

- 試験的な設定<br>
    基本的にデフォルトのまま「Next」<br>
    <left>
    <img src="https://dsm01pap004files.storage.live.com/y4mSJZtJQQaymQhIMfap57OrPdFqRe-fTWNRA0Ll7Eo6YTzvHI1ZlBxf4k4-F2TJpKiZSDFTFXjxbZy29JJcRp0xrNAT6kT16CA8gEzCtP8HJmDxwJbQCUm2qxgkYH2pvOOWnOjN5Uow4ohWc_3aszBzB72hufq3UN8Q44LH4vsic7Edu-XMjqC9XTjfiVJrkTx?width=490&height=388&cropmode=none" width=50%>
    </left>

4. Git Bashを実行する．<br>
    スタートメニューから「Git Bash」を実行する．<br>
    <font color="Red">おすすめ：</font> タスクバーの「Git Bash」を右クリックし，「タスクバーにピン留め」を選択

5. ユーザー名の設定<br>
    Gitで作業をした際に，作業者を識別するために「ユーザー名」と「メールアドレス」を下のコマンドをGit Bashで登録する必要がある．

    ###### ユーザー名の登録
    ```
    $ git config --global user.name ユーザー名
    ```

    ###### メールアドレスの登録
    ```
    $ git config --global user.email メールアドレス
    ```

---
## Ubuntu
1. Gitのインストール<br>
    ```
    $ sudo apt install git
    ```

2. ユーザー名の設定<br>
    Gitで作業をした際に，作業者を識別するために「ユーザー名」と「メールアドレス」を下のコマンドをGit Bashで登録する必要がある．
    ###### ユーザー名の登録
    ```
    $ git config --global user.name ユーザー名
    ```

    ###### メールアドレスの登録
    ```
    $ git config --global user.email メールアドレス
    ```
<br>

***
[ホーム](../Readme.md)