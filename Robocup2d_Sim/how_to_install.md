主に以下のサイトのインストールを個人用にまとめたもの<br>
(初心者でもわかりやすいように記述したもの)<br>
### 参考サイト

http://labusers.net/member/YoshitomoMatsubara/menu/blog-ja.php
http://rc-oz.osdn.jp/pukiwiki/index.php?2D%2FUbuntu%2F12.04
http://labusers.net/member/YoshitomoMatsubara/menu/blog-ja.php?path=20141020.html
https://github.com/ivanGzz/Phoenix2D/wiki/Installing-the-server
http://rctools.osdn.jp/pukiwiki/index.php?agent2d
http://rctools.osdn.jp/pukiwiki/index.php?librcsc
http://d.hatena.ne.jp/gumitaro2012/20130724

# 環境構築の流れ
0.必要な依存ライブラリ
  - Boostとか
  - Bisonは古いver

1.シュミレーション環境
  - rcssserver
  - rcssmonitor
  - rcsslogplayer

2.サンプルプログラムの導入
  - librcsc
  - Agent2d
  - (soccerwindow2)


# 0.必要な依存ライブラリのインストール
まずここでは必要な依存ライブラリのインストールを行います<br>
環境構築の前にかならず

    sudo apt-get update
でソフトウェアアップデートを行ってください

必要な依存ライブラリをapt-getコマンドでインストールします<br>
（参考したサイトではbisonを入れていますがバージョンが新しいため動きません<br>
今回はbisonを除外してインストールします）

    sudo apt-get install build-essential autoconf automake libtool flex libboost-all-dev libphonon-dev phonon-backend-gstreamer qt-sdk libaudio-dev libxt-dev libpng12-dev libglib2.0-dev libsm-dev libice-dev libxi-dev libxrender-dev libfreetype6-dev libfontconfig1-dev'

## 0.bisonのインストール
次にbisonをインストールします<br>
(参考URL：http://labusers.net/member/YoshitomoMatsubara/menu/blog-ja.php)<br>
（Wikiより：Bison（バイソン）とは構文解析器を生成するパーサジェネレータの一種であり、CコンパイラとしてのGCCのサポートのために[要出典]開発されたフリーソフトウェアである．）

    wget http://ftp.gnu.org/gnu/bison/bison-2.3.tar.gz

解凍，展開したディレクトリに移動

    ./configure
    make
    sudo make install


usr/local/bin内にbisonが生成されてればok

以上で必要なライブラリのインストールは終了

## 1.シュミレーション環境
http://rc-oz.osdn.jp/pukiwiki/index.php?2D%2FUbuntu%2F12.04<br>
上記を参考に進めます

以下のURLから最新版をダウンロード，展開する
http://sourceforge.net/projects/sserver/files/rcssserver/<br>
http://sourceforge.net/projects/sserver/files/rcssmonitor/<br>
http://sourceforge.net/projects/sserver/files/rcsslogplayer/<br>

  - rcssserver(15.2.2)
  - rcssmonitor(15.1.0)
  - rcsslogplayer(15.1.0)

ここで手順通り./configureすると…<br>
boost見つからないよ！！と文句を言われます<br>
そこで./configureにboostのライブラリを示すオプションを追加します

    ./configure  --with-boost-libdir=/usr/lib/x86_64-linux-gnu

そうすればエラーは出なくなると思います<br>
その後

    make
    sudo make install

とインストールしてあげるとbison同様にusr/local/bin内にrcsoccersim, rcsscilent，rcssserverが生成されてればok

最後に

    rcsoccersim
として起動してあげるとフィールドと22体のロボットが表示されます

以上でシュミレーション環境のインストールは終了


## 2.サンプルプログラム，ツールなどの導入
このままだとただインストールしただけなので動かす準備を行います<br>
☓：一からプログラムを作成するぞ！！<br>
◯：公開されているソースを改良するぞ！！<br>
使えるものは使っておきましょう

インストールするものは以下の4つです
  - librcsc
  - agent2d
  - soccerwindow2
  - fedit2

この章ではubuntuのバージョンで何か問題があることはないのでここを参考にインストールしてください
http://rctools.osdn.jp/pukiwiki/index.php?librcsc<br>
http://rctools.osdn.jp/pukiwiki/index.php?agent2d<br>
http://rctools.osdn.jp/pukiwiki/index.php?soccerwindow2<br>
http://rctools.osdn.jp/pukiwiki/index.php?fedit2<br>

以上です<br>
何かあったらコメントください<br>
