# Installation of Ubuntu 

## Install software
### 1. 下記ソフトウェアをダウンロード．
* [Chrome](https://www.google.com/chrome/?brand=FKPE&ds_kid=43700049288280964&gad_source=1&gclid=CjwKCAjwg8qzBhAoEiwAWagLrL3MZpdfFbQv_6euJ_aavVQ_h7sOY234eNiMKyjlj9rV4nSa6BW7YRoCOJIQAvD_BwE&gclsrc=aw.ds)

* [VScode](https://code.visualstudio.com/download)
* [Anaconda](https://www.anaconda.com/download)
* [Matlab](https://jp.mathworks.com/products/matlab.html)

<br>
(Option)

* [Slack](https://slack.com/downloads/linux)
* [Zoom](https://zoom.us/ja/download)
* [Webex](https://www.webex.com/ja/downloads.html)

## Set up procedure
### 1. GPUドライバーのインストール． <br>

メニューから「Additional Drivers」を実行する．<br>
"Using NVIDIA driver metapackage from nvidia-driver-5** (proprietary, tested)"を選択肢，インストールする．<br>
*Note* : RTX4000番台では，"\*\*\*-open"版は正常に認識されないのでインストールしない．<br>一方で，**RTX5000番台では，必ず"\*\*\*-open"版をインストールすること．**

### 2. aptによるソフトウェアの更新<br>
```
$ sudo apt update
$ sudo apt upgrade
```

### 3. ソフトウェアのインストール<br>

【インストール：apt】
```
$ sudo apt install nvidia-cuda-toolkit
$ sudo apt install ibus-mozc
$ sudo apt install git
$ sudo apt install ssh

# If you are building a client:
$ sudo apt install openssh-client

# If you are building a server:
$ sudo apt install openssh-server

```
別途，ソフトウェアをインストーラーからインストールする．
```
$ cd ./Downloads
$ sudo apt install ***
```
*Note* : ***は，Chrome, Slack, Vscode, Zoom, etc.

【インストール：bash】
```
$ bash ./***
```
Anacondaなどの拡張子が".sh"であるファイルは，"bash"でインストールする．<br>

**---Anacondaのインストール---**<br>
次の質問に質問に対して<br>
「running conda init?」<br>
「yes」と入力し，Enterを押す．<br>

*Note* : Anacondaをインストールする際は，"sudo"を付けないこと！

### 4. VSCodeの設定

Extensionsから下記をダウンロードする．<br>
Python, vscode icons, Bracke Pair Colorzation Toggler, Path Autocomplete, Markdown Preview Enhanced, Trailing space, Remote-ssh

また，フォントサイズを変更する．
`Editor: Font Size 16`

### 5. Matlabをインストール<br>
```
$ xhost +SI:localuser:root
```
"matlab_R20xx_glnax64.zip"を展開し，下記のコマンドに従う．
```
$ cd ./Downloads/matlab_R20xx_glnax64
$ sudo ./install
```
Login Nameは，terminalで`whoami`と入力することで確認可能．
Create symbolic iconに✓する．

**---Matlabのlauncherを表示 & キーボード設定---**<br>

Matlabアイコンを`wget`を用いてダウンロードする．
```
$ sudo wget http://upload.wikimedia.org/wikipedia/commons/2/21/Matlab_Logo.png -O /usr/share/icons/matlab.png
```
次に，ショートカットのためのファイル`matlab.desktop`を下記パスに作成する．
```
$ sudo nano /usr/share/applications/matlab.desktop
```
`matlab.desktop`には，下記の内容を記述する．（Matlabのversionは任意の数字に変更してください）．
```
[Desktop Entry]
Type=Application
Icon=/usr/share/icons/matlab.png
Name=MATLAB R2021a
Comment=Start MATLAB - The Language of Technical Computing
Exec=matlab -desktop
Categories=Development;
```
Matlabを起動し，<br>
`Preference -> Keybord -> Shortcut -> Windows Default Set`
で設定を変更する．

### 6. 別ディスクのマウント設定<br>

メニューから`Disks`を選択する．<br>
外部ディスクを任意のラベル名でフォーマットする．<br>
`Edit Mount Options -> Identify as Label=**`に変更する．

### (Option) サーバーPC用：自動スリープの無効
下記コマンドの有効性は未確認．<br>
スリープ無効コマンド
```
$ sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```
スリープ有効コマンド
```
$ sudo systemctl unmask sleep.target suspend.target hibernate.target hybrid-sleep.target
```
----
# Notes on Blackwell GPU (As of December 23, 2025)

RTX 5000 番台 GPU（Blackwell アーキテクチャ，Compute Capability sm_120）では，CUDA 12.8 未満の CUDA Toolkit を用いた環境で，CUDA Toolkit 依存パッケージの動作が不安定になる
事例が多く報告されています．

## 対応策

Ubuntu（特に 22.04 / 24.04）環境では，以下を基本方針とする．

- ✅ **NVIDIA Driver には触らない**
- ✅ **CUDA Toolkit のみを更新する**
- ❌ `apt install cuda` は使用しない（driver が混入する）
- ❌ Ubuntu 公式 NVIDIA パッケージと NVIDIA CUDA repo を混在させない

## CUDA Toolkit 12.8 のインストール方法 
（Toolkit のみ・Driver 非変更）

### 0. 現在のCUDAバージョンを確認
CUDA コンパイラの確認：
```
$ nvcc -V
```
Cuda compilation toolsのバージョンが出力される．
```
Cuda compilation tools, release 12.0, V12.0.140
```
バージョンが12.8 以下であれば，次以降の手順に従い更新する．

### 1. CUDA 12.8 local installer をダウンロード
```
$ wget https://developer.download.nvidia.com/compute/cuda/12.8.0/local_installers/cuda_12.8.0_570.86.10_linux.run
```
### 2. 実行権限を付与
```
$ chmod +x cuda_12.8.0_570.86.10_linux.run
```
### 3. Toolkit のみをインストール（driver / firmware なし）
```
$ sudo ./cuda_12.8.0_570.86.10_linux.run --toolkit --silent
```
この手順で下記をインストール可能です：
- nvcc
- CUDA runtime / 開発用ライブラリ
- CUDA ヘッダ・ツール群

### 4. 環境変数の設定（bash）
以下を ~/.bashrc に追記：
```
$ export CUDA_HOME=/usr/local/cuda-12.8
$ export PATH=/usr/local/cuda-12.8/bin:$PATH
$ export LD_LIBRARY_PATH=/usr/local/cuda-12.8/lib64:$LD_LIBRARY_PATH
```
変更を反映
```
source ~/.bashrc
```

### 5. 更新されたCUDAバージョンを確認
CUDA コンパイラの確認：
```
$ nvcc -V
```
Cuda compilation toolsのバージョンが出力される．
```
Cuda compilation tools, release 12.8, V12.8.61
```
また，nvcc のパスも確認：
```
$ which nvcc
```
最後に，NVIDIA Driver のバージョンが変更されていないか確認：
```
$ nvidia-smi
```

----
[Readme](Admin_Readme.md)