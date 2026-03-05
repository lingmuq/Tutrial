# Anacondaコマンド

Anacondaでよく使うコマンドです．

## Anaconda base管理コマンド
* baseの更新
```
$ conda update -n base conda
```
## 仮想環境用コマンド
* 空の仮想環境を構築
```
$ conda create -n [environment_name]
```

* 仮想環境を構築
```
$ conda create -n [environment_name] python=[version] anaconda
```

* 仮想環境を削除
```
$ conda remove -n [environment_name] --all
```

* 仮想環境の名前を変更（新しい名前でクローンを作成して古い環境を消す）
```
$ conda create -n [new_environment_name] --clone [old_environment_name]
$ conda remove -n [old_environment_name] -all
```
* 指定した仮想環境に切り替え
```
$ conda activate [environment_name]
```

* 指定した仮想環境を停止
```
$ conda deactivate [environment_name]
```

* 作成したすべての仮想環境を確認
```
$ conda info -e
```

## パッケージ関連コマンド
* パッケージのインストール（バージョン指定なし）
```
$ conda install [package_name]
```

* パッケージのインストール（バージョン指定あり）
```
$ conda install [package_name]==*.*.*
```

* パッケージのアンインストール
```
$ conda uninstall [package_name]
```

* パッケージを更新
```
$ conda update [package_name]
```

* パッケージをすべて更新
```
$ conda update --all
```

* パッケージを検索
```
$ conda search [package_name]
```

* インストール済みのパッケージをすべて表示
```
$ conda list
```

* 指定したインストール済みのパッケージを表示
```
$ conda list [package_name]
```

----
[Readme](Admin_Readme.md)