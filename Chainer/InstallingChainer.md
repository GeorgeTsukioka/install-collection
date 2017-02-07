# chainerのインストール方法に関して
参考URL1:Ubuntu 14.04.3 LTS に Chainer をインストールする , http://tanakahx.hatenablog.com/entry/2015/10/12/214738(参照日:2015年11月30日)<br>
参考URL2:Chainer 1.5のインストールがうまくいかない人への非公式なTips , http://qiita.com/unnonouno/items/c491b6df59352159cbf0(参照日:2015年11月30日)<br>
参考URL3:Cython のインストール , http://omake.accense.com/static/doc-ja/cython/src/quickstart/install.html(参照日:2015年11月30日)<br>

## 環境
  * VMware
  * ubuntu14.04 64bit

公式サイトでインストール方法は以下のコマンドを打つだけで簡単と謳っている

    pip install chainer

しかし，ubuntuをインストールしたばかりなどではpipが入っていないため

    sudo apt-get install python-pip

をインストールする必要がある．その後pipでインストールしてもエラーが発生する<br>
その場合は他にインストールしないないものがある
以下のコマンドを打ってから再度chainerをインストールを行うときちんとインストールされる

    sudo apt-get install python-dev python-numpy python-scipy libhdf5-dev cython

    pip install chainer

エラーが表示された場合エラー通りに何かをインストールしたり更新する必要がある<br>
pipを最新版にする必要があったので
    curl -O https://bootstrap.pypa.io/get-pip.py
    sudo python get-pip.py

を行ってchainerをインストールした．<br>
エラーが起きずにインストールできた場合はmnistのサンプルを実行し，ちゃんとインストールが出来たかを確認
