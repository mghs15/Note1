# TippecanoeをWSL上に作る
WSLに入れた時の手順メモ

## WSLの導入

以下のページから目的のディストリビューションのAPPXを落とす。
https://docs.microsoft.com/ja-jp/windows/wsl/install-win10#step-6---install-your-linux-distribution-of-choice

その後、拡張子をAPPXからZIPに変更する。

ZIPを展開し、中のEXEを実行する。


## デフォルトユーザ

### 新規ユーザ追加
```
sudo userdel -r 削除したいユーザー名
sudo adduser 新しいユーザー名
```
> https://qiita.com/RYOSKATE/items/81b564b2ab281ec7f27d

### sudoグループに追加
```
wsl -u root
usermod -G sudo 設定変更するユーザ名
```

### WSL起動時のデフォルトユーザの変更
```
.\ubuntu2004.exe config --default-user root
```
または/etc/wsl.confに以下の記入をする。
```
[user]
default=username
```
> https://github.com/microsoft/WSL/issues/3974

### とりあえず、rootでのSSHログイン禁止
```
sudo vi /etc/ssh/sshd_config
```
> https://pointsandlines.jp/server-infra/linux-no-root-login


## WSL再起動
```
wsl.exe --shutdown
```
> https://kagasu.hatenablog.com/entry/2020/01/02/155532


## Tippecanoe
基本は、[TippecanoeのREADME](https://github.com/mapbox/tippecanoe)に従う。
```
sudo apt-get install build-essential libsqlite3-dev zlib1g-dev
```
（以下の4行不要かも。最初にg++のバージョン確認）
```
sudo add-apt-repository -y ppa:ubuntu-toolchain-r/test
sudo apt-get update -y
sudo apt-get install -y g++-7
export CXX=g++-7
```
```
make
make install
```

## Node
```
sudo apt install nodejs
nodejs -v
```

（エラー対応。Windows側のnpmを見てしまうみたい。）
```
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
sudo apt install npm
```
> https://github.com/microsoft/WSL/issues/3882

```
sudo npm install n -g
sudo n stable
```
> https://moewe-net.com/windows/wsl-install