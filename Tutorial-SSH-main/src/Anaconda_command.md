# Anacondaコマンド

Anacondaでよく使うコマンドです．

## 仮想環境用コマンド
* 空の仮想環境を構築
```
$ conda create -n [environment_name]
```

* 仮想環境を削除
```
$ conda remove -n [environment_name] --all
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

* インストール済みのパッケージをすべて表示
```
$ conda list
```

----
[Readme](../README.md)