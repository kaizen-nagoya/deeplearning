---
title: あなたもdocker, 私もdocker。docker(130)
tags: Qiitaエンジニアフェスタ_Dockerシステム構成 Docker GCC 新人プログラマ応援 CountdownCalendar2021
author: kaizen_nagoya
---
### The Qiita article cannot be updated due to system issues. Please refer to GitHub for the latest version.

Docker上のみでシステムを作るときの構成
https://qiita.com/official-events/339b6440dbd578f4f66f

参加記事です。

優秀賞 をいただきました。ありがとうございます。

Qiita エンジニアフェスタ 2021 プレゼント企画結果発表
https://blog.qiita.com/engineer-festa-presents-winners-2021/

Qiita 10周年記念イベント 「10年前の自分に伝えたい、勉強しておきたかった技術」
https://qiita.com/official-events/1e99fc384200c38548fd

参加記事の、

データサイエンティストの気づき「勉強だけして仕事に役立てない人。大嫌い！」。『それ自分かも！』ってなった。
https://qiita.com/kaizen_nagoya/items/d85830d58d8dd7f71d07

で参照させていただいています。そちらもLGTM(Look Good To Me＝いいね）よろしく。

 <この項は書きかけです。順次追記します。>
# dockerは保育園、幼稚園のお子様にお勧め。
むつかしい導入手順を踏まなくても、導入結果がすぐに利用できます。

同様に、高齢者の方にもお勧め。

６５歳からのプログラミング入門。docker(126)転職(16)
https://qiita.com/kaizen_nagoya/items/1561f910c275b22d7c9f

# 環境
普段, dockerを使っている環境は、
macOSHigh Sierra ver. 10.13.6
メモリ16GB, intel Core i5
HDD 250GB, 空 ~~6~~ 20GB (空きが少なくてtwitterが動かなくなった。増やしました）です。

ディスクの空きが少ないのは危険です。良い子は真似しないでください。

自分でdockerfile, docker-composeを作ったり、積極的に使っていません。ごめんなさい。

資料集 [あなたもdocker私もdocker一覧] docker(0) 
https://qiita.com/kaizen_nagoya/items/45699eefd62677f69c1d

に１４０ほど記事を書いています。また、下の機械学習のdocker上での実験一覧など、合計で３００近い記事を書いているような気がします。タグを順次追記するようにします。

dockerで実現したいことが似ている場合は、それらを参照くださると幸いです。

# 表題「あなたもdocker, 私もdocker。」について

「あなたもdocker」のあなたとは、下で紹介しているgccのクロスコンパイラの環境を構築してくださった斉藤直希さんのことです。
dockerfileを作り、docker-composeをしています。

「私もdocker」の私は、@kaizen_nagoyaのことです。斉藤直希さんはじめ、何人かの方がお造りになられたdockerfileとdocker-composeの成果を利用させていただいて、結果をdocker hubに登録させていただいています。「Docker上のみでシステムを作るときの構成」の趣旨どおり、私の作業は、docker run, docker commit, docker push以外は、すべてdockerのみでの作業です。

そこで、私が登録したdocker hubの内容を利用してくださるあなたを、「私」として記載しようとしています。あなたもdockerを利用してくださるなら、「私もdocker」と思ってくださいねっていう願いを込めて。

### 20210731編集 docker hubのダウンロードの多い記事の順番に項目を並べ直しました。

# 1. jq 
自分のdocker hubでダウンロードが圧倒的に多いのがjq.

Web系の資料を少し充実すると、ダウンロード数が急増しそうな気配。
これから１年は、dockerでjsonを10記事目標で書きます。
jqだけでいい場合は、

```macOS:bash
$  docker run -it ubuntu /bin/bash
```
dockerのubuntuが起動したら。

```ubuntu:bsh
# apt update; apt -y upgrade; apt install -y curl jq vim sudo
```

# 2. python
dockerの使い道の2つ目は、python.

機械学習の教育の助手を担当した。自宅または仕事場のWindowsにpytohnを導入するのに失敗した人たちが大勢いた。演習の落ちこぼれの原因がpython導入であることがわかった。

M.S.WindowsにPython3 (Anaconda3) を導入する（7つの罠）
https://qiita.com/kaizen_nagoya/items/7bfd7ecdc4e8edcbd679

自分のQiitaの記事で、viewsが圧倒的に一番で、161,987 viewsある。
二番目が
プログラマが知っているとよい色使い(JIS安全色)
https://qiita.com/kaizen_nagoya/items/cb7eb3199b0b98904a35

の82,114 viewsだから約2倍。

その後、dockerにPythonを導入してもらう方が楽かなって思うようになった。

docker(18) なぜdockerでpython/Rを使って機械学習するか 書籍・ソース一覧作成中 (目標100)
https://qiita.com/kaizen_nagoya/items/ddd12477544bf5ba85e2

dockerに書籍のソースコードを読み込んで、動かす実験を順次してきた。

## python 学習
pythonの言語教育を担当することになり、python のいろいろな版を利用するには、dockerが最適であると感じた。

pyenvなど、いろいろなpythonの複数の版を切り替える方法は面倒くさいだけでなく、python 初心者に使い方を教える時間が無駄だと感じた。

```macOS:bash
$ docker run -it continuumio/anaconda3 /bin/bash
```

言語処理100本ノックは、こちらの記事から参考にしてみてください。

言語処理100本ノック 2015(python) 落ち穂拾い 第1章: 準備運動
https://qiita.com/kaizen_nagoya/items/ee1b625b0b65cd63d42a

言語処理100本ノックをdockerで。python覚えるのに最適。docker(19) python(1)
https://qiita.com/kaizen_nagoya/items/7e7eb7c543e0c18438c4

#  3. gcc
dockerの使い道の最初は、gccのクロスコンパイル.
macOSでgccのクロスコンパイラをコンパイルしようとして１日かけてもうまく行かず、斉藤直希さんに相談し、docker上でgccクロスコンパイラを構築してもらった。

Dockerをどっかーらどうやって使えばいいんでしょう。TOPPERS/FMP on RaspberryPi with Macintosh編 ５つの関門「名古屋のIoTは名古屋のOSで」docker (37) 
https://qiita.com/kaizen_nagoya/items/9c46c6da8ceb64d2d7af

gccだけ使いたい場合は、

```macOS:bash
$  docker run -it gcc /bin/bash
```

例えば、
Misra Example Suite at docker コンパイル完了までの道のり。docker(200) 
https://qiita.com/kaizen_nagoya/items/71f04a0204d5a1114577

# 4. COBOL
どんな言語でも、簡単に構築することができる。上位１６に出てくる次はCOBOL

他のシステムは、いろいろなライブラリをいっぱい入れている。
cobolは、ライブラリをあまり入れてない。私のdocker hubから利用することをお勧めしたいかも。

```macOS:bash
$ docker run -it kaizenjapan/cobol /bin/bash
```

COBOLを40年ぶりにうごかしてみた:dockerでcobol。プログラムちょい替え（4）
https://qiita.com/kaizen_nagoya/items/9d9a216ce1b7b05dbb43

# 5. R
Raspberry PIのRaspbianでもRは使えた。
dockerで動かして結果確認などをしている。

```macOS:bash
$ docker run -it kazienjapan/r-master /bin/bash
```

dockerでR 難関いくつ？ docker(125) dockerで機械学習(104) 環境構築(4)
https://qiita.com/kaizen_nagoya/items/5fb44773bc38574bcf1c

「入門 機械学習」Drew Conway, John Myles White 著。dockerで機械学習(71) with R (1)
https://qiita.com/kaizen_nagoya/items/e3722c04ae35e82ecca2
データサイエンスのための統計学入門 ―予測、分類、統計モデリング、統計的機械学習とRプログラミング」Peter Bruce、Andrew Bruce　著。dockerで機械学習(72) with R (2)「
https://qiita.com/kaizen_nagoya/items/479e3283a2d030726254
RとKerasによるディープラーニング」François Chollet、J. J. Allaire著。dockerで機械学習(73) with R (3)「
https://qiita.com/kaizen_nagoya/items/57b0d84b3ce4f754485d
Introduction to Machine Learning with R By Scott Burger著。dockerで機械学習(74) with R (4)
https://qiita.com/kaizen_nagoya/items/be23896636af7a7b014d
「R Deep Learning Cookbook」 Philippe Remy著。dockerで機械学習(75) with R(5)
https://qiita.com/kaizen_nagoya/items/4d6d4b5d9739bcffbf02
Mastering Machine Learning with R 」Cory Lesmeister著。dockerで機械学習(76) with R (6)「
https://qiita.com/kaizen_nagoya/items/c3d51cdd3b811dac4d26
「「Rによる機械学習」の勉強履歴（1）」後追い: dockerで機械学習(77) with R (7)
https://qiita.com/kaizen_nagoya/items/68170a86b1b3dd5e596b
Machine-Learning-with-R-Cookbook-Second-Edition-master。dockerで機械学習(78) with R (8)
https://qiita.com/kaizen_nagoya/items/cbbed4d49ebb9c479816

# 6. FORTRAN
FORTANもCOBOL同様簡単に導入できる。
ここではdocker hubからの利用を勧めてみる。

```macOS:bash
$ docker run -it kazienjapan/fortran /bin/bash
```

プログラムちょい替え（11) Fortran 多次元配列のアクセス順序による計算時間の違い
https://qiita.com/kaizen_nagoya/items/3d657649d74fdd753bad

連立微分方程式のPade近似解法　Fortran手による最適化とコンパイラの最適化、誤差の評価
https://qiita.com/kaizen_nagoya/items/c55d29f0d7e9ebd07a31

# 7. ruby
rubyのちいちゃいやつがmruby

```macOS:bash
$ docker run -it kaizenjapan/mruby /bin/bash
```

mruby/cをdocker hubにあげた。要点５つ課題６つ。docker(129)
https://qiita.com/kaizen_nagoya/items/b908c594ff9d829683b5

# 8. 英語辞書作成

dockerの使い道の３つ目は、英語の文献を読んで単語帳を作る時。

「量子アニーリングの基礎」を読む勉強会を開催した。

「量子アニーリングの基礎」を読む
https://qiita.com/kaizen_nagoya/items/29580dc526e142cb64e9

で参考文献の半分以上が英語論文だった。順次単語帳を作った。

プログラムちょい替え（10）英語(14) 単語帳作成 dockerで（文字コード対応）量子計算機　arXiv掲載　西森 秀稔　論文(shell, awk), docker(82)
https://qiita.com/kaizen_nagoya/items/319672853519990cee42

この時は、素のubuntuから始める。

```macOS:bash
$  docker run -it ubuntu /bin/bash
```
dockerが起動したら

```utunbu:bash
# apt install -y poppler-utils vim
```

# 一覧
docker hubの登録が100を超え、保守作業をはじめました。docker(122)
https://qiita.com/kaizen_nagoya/items/3dcb6dab32ed25f66cd8

http://hub.docker.com/u/kaizenjapan/
のダウンロード上位１６。

Qiitaの記事は、１対１対応ではないが、なるべく最初にそのdocker hubに登録した記事を示すように検索中です。

|no.|name|star|downloads|language|Qiita|
|:----|:----|:----|:----|:----|:----|
|1|jq|0|481|jq|docker で  jq。docker(47)  https://qiita.com/kaizen_nagoya/items/8b35775c354cac36093b|
|2|anaconda-deep-1|0|121|python|ゼロから作るDeep Learning - Pythonで学ぶディープラーニングの理論と実装」斎藤 康毅 著。dockerで機械学習(1) with anaconda(1)「https://qiita.com/kaizen_nagoya/items/a7e94ef6dca128d035ab|
|3|anaconda-keras|0|102|python|「直感Deep Learning」Antonio Gulli、Sujit Pal著。dockerで機械学習(3) with anaconda(3) https://qiita.com/kaizen_nagoya/items/483ae708c71c88419c32|
|4|anaconda-deep|0|90| python|
|5|anaconda-keras-ten|0|58|python|dockerで機械学習(9) with anaconda(9)「pythonではじめる機械学習」Andreas C. Muller, Sarah Guido 著 https://qiita.com/kaizen_nagoya/items/0960a286b61d50381925|
|6|anaconda-handson|0|52|python|
|7|anaconda-francois|0|49| python|dockerで機械学習(17) with anaconda(17)「PythonとKerasによるディープラーニング」 ：Francois Chollet著 https://qiita.com/kaizen_nagoya/items/bce4fa73560370733ea2 {
|8|dockertoppersfmprpi64_fmp|0|48|gcc|Dockerをどっかーらどうやって使えばいいんでしょう。TOPPERS/FMP on RaspberryPi with Macintosh編 ５つの関門「名古屋のIoTは名古屋のOSで」docker (37)https://qiita.com/kaizen_nagoya/items/9c46c6da8ceb64d2d7af|
|9|cobol|0|47|cobol |COBOLを40年ぶりにうごかしてみた:dockerでcobol, docker(81)プログラムちょい替え（4）https://qiita.com/kaizen_nagoya/items/9d9a216ce1b7b05dbb43|
|10|100pon|0|44| python|言語処理100本ノックをdockerで。python覚えるのに最適。docker(19) python(1) https://qiita.com/kaizen_nagoya/items/7e7eb7c543e0c18438c4|
|11|conda3-amueller|0|41| python|dockerで機械学習(9) with anaconda(9)「pythonではじめる機械学習」Andreas C. Muller, Sarah Guido 著 https://qiita.com/kaizen_nagoya/items/0960a286b61d50381925 |
|12|r-master|0|41|r|@kazuo_reve「「Rによる機械学習」の勉強履歴（1）」後追い: dockerで機械学習(77) with R (7) https://qiita.com/kaizen_nagoya/items/68170a86b1b3dd5e596b | 
|13|docker-ubuntu10-ndev|0|38|python|dockerで機械学習(105)環境構築(5)docker関連ファイルの管理 https://qiita.com/kaizen_nagoya/items/4f03df9a42c923087b5d|
|14|anaconda-nikhil|0|37| python|dockerで機械学習(31) with anaconda(31)「Fundamentals of Deep Learning」 By Nikhil Buduma https://qiita.com/kaizen_nagoya/items/4d9e037aef317b00be10
|15|fortran|0|37|fortran| Fortran 多次元配列のアクセス順序による計算時間の違い。プログラムちょい替え（11) https://qiita.com/kaizen_nagoya/items/3d657649d74fdd753bad|
|16|mrubyc|0|36|ruby | mruby/cをdocker hubにあげた。要点５つ課題６つ。docker(129) https://qiita.com/kaizen_nagoya/items/b908c594ff9d829683b5|

kerasの導入少し手間取りました。保存もうまくいかなかったこともある。

100本ノックの全部を保存したものは、エラーがでちゃうようで現在調査中です。

# 更新
どの場合も、dockerが立ち上がったら、

```ubuntu:bash
# apt update; apt -y upgrade apt; 
```

をまずしよう。

全部で300くらいdockerを使った記事を書いているような気がする。

エラーがあった時に、エラーメッセージで検索する場合、　docker kaizen_nagoyaの文字を入れるとずばりヒットするかも。docker関連のエラーをなるべく記事にしています。

# ディスクの共有
オープンソースじゃないソースのコンパイルをしようとするときは、
ディスクの内容を公開せずに作業ができる。

```macOs:bash
$  docker run -v /tmp/fortran:/tmp/fortran -it  kazienjapan/fortran /bin/bash
```

あらかじめ、dockerを起動するシステムに/tmp/fortranというフォルダがあり、
そこにソースコードを入れておけば、起動したdockerでも、/tmp/fortranという
フォルダのソースをコンパイルできる。作業後に、そのフォルダは exitすれば
docker hub側に残ることはない。

# docker hubへの保存。

例：jq
docker commit してdocker pushする。
dockerを起動したコマンドプロンプトで実行する。
dockerの中では実行できない。

```macos:bash
$ docker commit d48bcf70b686 kaizenjapan/jq
$ docker push kaizenjapan/jq
```
16進数文字列は、dockerのコマンドに現れているやつ。

# port利用

```
$ docker run -it -p 8888:8888  kaizenjapan/anaconda-alice /bin/bash 
```
docker -p, 画面表示 。docker(3)
https://qiita.com/kaizen_nagoya/items/a353862ec69fccce8bc2

# 困りごと
### 1. loginできない。
アプリは起動し、メニューからloginしているはずなのに、
dockerコマンド打つと、loginしてないと怒られることがある。

コマンドで、docker login し直すといいことがある。

それでも駄目な時は、OSを再起動して、dockerアプリでログインし、
コマンドでもloginするといいことがある。MS Windowsでも類似の経験あります。

docker(80)「DockerでPHP7.0×Apacheの環境を構築する@kurkuru」IT業界新人利用時の１6の壁(mac mini編）
https://qiita.com/kaizen_nagoya/items/315e8d05a6eef00b56d1

### 2. run, pushできない
自分の経験では綴りがちがっていることが一番多い。
anaconda3ではだめで、continuumio/anaconda3じゃないといけないみたいに全部指定しないと駄目なことがある。
その次には、同じ名前で作業していたりとか。

docker(17) docker入門の入門　５つの壁
https://qiita.com/kaizen_nagoya/items/e73ceab051a5556a652c

### 3. ブラウザで確認したい。
今回の趣旨とは少しずれるかもしれないが、
dockerで動作させたものを、ブラウザで確認したいことがしばしばある。

python でjupiter notebookを使うときや、
javascript, PHPなどで作ったソフトを確かめる時など。

### 4. HDD等の空きがない。
dockerをいっぱい立ち上げてrm, rmiするといいかも。

docker(9) rmiのための順番
https://qiita.com/kaizen_nagoya/items/0bc05d08cf18af4a8801

### 5. メモリが足りない
機械学習などをしているとdockerに10GB以上割り当ててないと、処理が進まないことがある。本体を32GBメモリにしてdockerに24GB割り当てると結構楽かも。

# この作業のエラー
今日のdocker error :Error response from daemon: conflict: unable to delete 解決
https://qiita.com/kaizen_nagoya/items/a486385d6af636c98f0a

# 新人
新人の方によく展開している有益な情報
https://qiita.com/kazuo_reve/items/d1a3f0ee48e24bba38f1

マネージャ・リーダーの私にとって有益な知見が得られた書籍
https://qiita.com/kazuo_reve/items/6976029e72763ea73245

新人(学生)を指導するよりも新人(学生)に指導してもらった方が効率的。仮説（139）
https://qiita.com/kaizen_nagoya/items/db993b1536055029f7c8

# 参考資料(reference)
第11回 TOPPERS活用アイデア・アプリケーション開発コンテスト
https://qiita.com/kaizen_nagoya/items/91162a9b258a2a06f5e0

ひょっとしたら、この部門への投稿の表題を変えて、コンテストに応募するのも手かも。
TOPPERS のAUTOSARへの貢献(更新中), AUTOSAR(15)
https://qiita.com/kaizen_nagoya/items/d363cf06e2176207b391

AUTOSARとSimulink: Adaptive Platform, Classic Platformとマルチコア対応を含めた共通化を目指して
https://qiita.com/kaizen_nagoya/items/d613b0b14bfd91989a13

TOPPERS の AUTOSAR への貢献 II (改定中)
https://qiita.com/kaizen_nagoya/items/4614c04cfff70a241f77

人生で影響を受けた本100冊。Youtube(3)
https://qiita.com/kaizen_nagoya/items/16af53acbb147a94172e

 今まで書いてよかった技術書を紹介しよう！ 
https://qiita.com/kaizen_nagoya/items/d31b7c158541d345a7ef

docker入門の入門　9つの壁。docker(17)
https://qiita.com/kaizen_nagoya/items/e73ceab051a5556a652c

docker 入門。docker(2)
https://qiita.com/kaizen_nagoya/items/2f31319e40ddaa0bf8a5

プログラミング言語教育のXYZ。Youtube(1) 仮説・検証（52）
https://qiita.com/kaizen_nagoya/items/1950c5810fb5c0b07be4

技術士　設計側としての情報工学・電気・電子と、設計対象としての全分野
https://qiita.com/kaizen_nagoya/items/37be048c2715465787be

 開発環境を豊かにする開発事例　過去・現在・未来 
https://qiita.com/kaizen_nagoya/items/d9bf0c2c671fe7f1c749

 Microsoftとの歴史　Cコンパイラを中心に 
https://qiita.com/kaizen_nagoya/items/d7c0cc257e99de0573cf
　Qiitaエンジニアフェスタ_ブラウザ選手権
https://qiita.com/kaizen_nagoya/items/98c4c7f911aa47465087
 
 Qiitaエンジニアフェスタ_StaticWebApps に参加するまで
https://qiita.com/kaizen_nagoya/items/1a1f53926325d872821f
　
 TOPPERS ソースを積み上げよう
https://qiita.com/kaizen_nagoya/items/65c15aed086f2da0928d

技術書「Rubyソースコード完全解説」 と 「docker で ruby」構築
https://qiita.com/kaizen_nagoya/items/a00fec16fb43e6e9071d

会計と技術　工業簿記、原価計算に加えて
https://qiita.com/kaizen_nagoya/items/66b0c57d99b689acbb8d

UMLモデリングの本質
https://qiita.com/kaizen_nagoya/items/bc6ac386af27530eb78a
Code Complete：goto論争の終焉
https://qiita.com/kaizen_nagoya/items/82c7939f442cbd5fce37
RTL設計スタイルガイド Verilog HDL編
https://qiita.com/kaizen_nagoya/items/c883b9aab40c53c1d259
定量分析の教科書
https://qiita.com/kaizen_nagoya/items/c79b7b2356032f3817e3
Githubで開発環境構築から教育環境構築、教材作成へ
https://qiita.com/kaizen_nagoya/items/493bdd22c7d318402fe2

名刺代わりの技術書10選
https://qiita.com/kaizen_nagoya/items/dc497dcaa5a304fc96c8

一覧の一覧( The directory of directories of mine.) Qiita(100)
https://qiita.com/kaizen_nagoya/items/7eb0e006543886138f39

プログラマが知っていると良い「公序良俗」
https://qiita.com/kaizen_nagoya/items/9fe7c0dfac2fbd77a945

小川清最終講義、小川清最終講義（再）計画, Ethernet(100) 英語(100) 安全(100)
https://qiita.com/kaizen_nagoya/items/e2df642e3951e35e6a53

http://b.hatena.ne.jp/guide/bbutton

さいごまでおよみいただきありがとうございました。
https://qiita.com/kaizen_nagoya/items/3387ded65f55a8303817

 ＜この記事は個人の過去の経験に基づく個人の感想です。現在所属する組織、業務とは関係がありません。＞
### 文書履歴(document history)
ver. 0.01 初稿 20210724
ver. 0.02 一覧追記 20210725
ver. 0.03 順番入れ替え、参考URL追記 20210731 午後4時
ver. 0.04 ディスク共有 追記 20210731 午後5時
ver. 0.05 R 追記 20210731 午後6時
ver. 0.06 参考資料追記 20210808
ver. 0.07 参考資料追記 20210809
ver. 0.08 斉藤直希さんが読んだであろう箇所の表現を補足 20210817
ver. 0.09 編集 20210902
ver. 0.10 Qiita エンジニアフェスタ 2021 優秀賞 をいただきました。ありがとうございます。20210914
ver. 0.11 「データサイエンティストの気づき「勉強だけして仕事に役立てない人。大嫌い！」。『それ自分かも！』ってなった。」参照追記 20210921
ver. 0.12 言語処理100本ノックをdockerで。python覚えるのに最適。docker(19) python(1) 追記 20211212
ver. 0.13 URL追記 20211218
ver. 0.14 dockerは保育園、幼稚園のお子様にお勧め。20220202
ver. 0.15 ありがとう追記 20230423
### 最後までおよみいただきありがとうございました。
いいね　💚、フォローをお願いします。
####  Thank you very much for reading to the last sentence.
Please press the like icon 💚　and follow me for your happy life.

<a href="https://b.hatena.ne.jp/entry/s/qiita.com/kaizen_nagoya/items/8f2746f10f30b575d0a8" class="hatena-bookmark-button" data-hatena-bookmark-layout="basic-label-counter" data-hatena-bookmark-lang="ja" title="このエントリーをはてなブックマークに追加"><img src="https://b.st-hatena.com/images/v4/public/entry-button/button-only@2x.png" alt="このエントリーをはてなブックマークに追加" width="20" height="20" style="border: none;" /></a><script type="text/javascript" src="https://b.st-hatena.com/js/bookmark_button.js" charset="utf-8" async="async"></script>
