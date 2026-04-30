---
title: docker(18)でpython(10)/Rで機械学習する 書籍/ソース一覧 AI(36)
tags: Docker Python 機械学習 DeepLearning CountdownCalendar2022
author: kaizen_nagoya
slide: fals
---
### The Qiita article cannot be updated due to system issues. Please refer to GitHub for the latest version.
# 機械学習
機械学習を操るのに、手がかりとして、確率か統計（できれば両方）を勉強しているとよい。

実際には、原理を理解するか、プログラムとデータをたくさん操って身につけていくののどちらでもよい。ここでは、たくさん操るために、世の中で公開されているプログラムを操っていくことを目標とします。

<この項は書きかけです。順次追記します。>
This article is not completed. I will add some words in order.

# 環境構築
docker上に機械学習(machine learning)の環境を構築中です。
いつでも、どこでも作業を再開し、保存できるようにするためです。

機械学習(machine learning)・深層学習(deep learning)で検索可能な書籍で、ソースコードの半分以上を公開しているもの、または公開の許諾を与えているものを対象にします。

もし、よさげな資料がありましたら、ご紹介くださると幸いです。

## なぜdockerで機械学習するか
おおまかに３つ理由があります。
１　初めて参入する人の敷居を下げる。
２　多くの人と同じ環境で動作させ、動作の再現性を確認する。
３　作業時間の並列化・短縮

## １　初めて参入する人の敷居を下げる。
機械学習をするためには、これこれのシステムが必要だ。
という制約が、大きな壁にならないことを考えています。
dockerの導入もこの一つの壁です。

docker どっかーら、どーやってもエラーばっかり。dockerで機械学習(101) 環境構築(1) 
https://qiita.com/kaizen_nagoya/items/690d806a4760d9b9e040

Docker for Windows。dockerで機械学習(102) 環境構築(2)
https://qiita.com/kaizen_nagoya/items/c4daa5cf52e9f0c2c002

### 1.1 どの言語で行うか。
python, R, Java, ...

### 1.2 pythonだとすれば2か3か.どのdistributionか。
docker(19) 言語処理100本ノックをdockerで。python覚えるのに最適。
https://qiita.com/kaizen_nagoya/items/7e7eb7c543e0c18438c4

#### 1.2.1 python3
基本はPython3, ただし、Python2で動かすことを前提としたソースはpython2でまず動かす。python3で動くように書き直すのは、手があれば。

Raspberry PIのRaspbianでは、python2, python3がどちらも入っている。

#### 1.2.2 anaconda
Python3, Python2はどのdistirbutionか。
ひとまずpython3のanaconda。

anacondaの課題はディスクの容量が大きくなること。
macOSがpython2が最初から入っていて、pyenvなどの環境設定の道具はとても大変。

windowsでは、dockerを使わないと次のように大変。

Windows(M.S.)にPython3(Anaconda3)を導入する（7つの罠）
https://qiita.com/kaizen_nagoya/items/7bfd7ecdc4e8edcbd679

Windows(M.S.) にAnaconda3(python3)を　2019年版
https://qiita.com/kaizen_nagoya/items/c05c0d690fcfd3402534

#### 1.2.3 conda ときどきpip
condaで導入できるものはconda. 
condaにないものはpip.

### 1.3 python/R以外にはどの言語で確認すればよいか。
一つの言語に依存することは、制約になるかもしれません。
pythonで動かしたことを、Rでも同じように扱えると嬉しい。

それ以外には、JAVA, C++, その他の言語も考えてみましょう。

## ２　多くの人と同じ環境で動作させ、動作の再現性を確認する。
参入の敷居を下げるだけでなく、
同じ環境で動作させれば、
作業の再現性が高くなる。

システムの保守、改良の手間が省ける。

## ３　作業時間の並列化・短縮
参入の敷居を下げること、保守性を高くすることにも通じているが、
ソフトウェアの導入時間を短くすることも大切である。

dockerにすれば必ず時間が短縮するというわけではない。
docker fileに無駄なことを書いたり、
docker hubにあげるシステムに無駄なファイルが多ければ、
時間は短縮しないかもしれない。

## 3.1 それぞれの本ごとにdockerを用意する
最初は、別々に用意されている方が、無駄がないかもしれない。

## 3.2 複数の本を同一の環境で処理する
どうせ複数の本のプログラムを試すのであれば、
複数の本に対応していた方がよいかもしれない。

## 3.3 CPUのマルチコア対応、クラウド対応
並列処理して、高速化を図る。

Mac上のDockerでホストマシンのCPUコアを最大限に使う
https://qiita.com/Yuhsak/items/d1438d83e480a93423c9

## 3.4 捨てるのが容易
エラーがでまくって、にっちもさっちもいかなくなった場合、そこまでのエラーが出た経緯、エラーだけ記録して、まるっと終了(exit)すれば、何もしなくても捨てることができる。

不要なimageは、後ほど、docker rmi image番号すればよい。

環境を消したり、ファイルを消したり、複雑なことをしないと綺麗にならないこれまでの経験からすれば、嘘のように簡単。

# お詫び(apology)
いくつかの記事は、途中でエラーを解決できずに止まっています。コメント等でご教示くださると幸いです。

## ディスク full
いくつかの作業は、ディスクがいっぱいなため、うまくいっていません。
現在、

docker ps -a 
docker rm

docker images
docker rmi

で削除中です。今、しばらくおまちください。

## pythonコード修正
画面に表示するものは、ファイル出力に変更。

あるライブラリの版との可搬性のためコードを修正中です。

## R package install
Rでうまくpackageがinstallできないことがありました。
今は、ファイル読み込みに失敗することがあります。

今日のdocker error: RStudio （解決）->ファイルエラー等
https://qiita.com/kaizen_nagoya/items/e1a757874e1e3e2c9765

下記記事を参考に対応を考える。

R ScriptやR Markdownからinstall.packages()を呼び出す場合はレポジトリを指定しないとエラーになる
https://qiita.com/maech/items/03b9566fb0fe940e1736

# 目標(goal)
~~dockerで機械学習を10項目作成予定。10月末目標~~ 20181008目標達成

~~年内~~ 10月中に30項目。年~~度~~末までに~~60項目。年度末までに~~100項目。

環境設定の記事を~~30項目~~20項目くらい、書籍は~~70冊~~80冊目標。うち、Python 50冊。R、20冊。C++, Java等合計10冊。年度末までに書籍で120冊（もしあれば）

# 一覧 54項目。1-41(python), 51-58(R), 71-77(others), 101-105(環境)
|  | books |
|:--|--:|
| python | 41 |
| R | 8 |
| others | 7 |
| sum | 56 |
| Env. | 5 |
| total | 61 |

## with anaconda(python)
「ゼロから作るDeep Learning - Pythonで学ぶディープラーニングの理論と実装」斎藤 康毅 著。dockerで機械学習 with anaconda(1)
https://qiita.com/kaizen_nagoya/items/a7e94ef6dca128d035ab

「ゼロから作るDeep Learning2自然言語処理編」斎藤 康毅 著。dockerで機械学習with anaconda(2)
https://qiita.com/kaizen_nagoya/items/3b80dfc76933cea522c6

「直感Deep Learning」Antonio Gulli、Sujit Pal　第1章,第2章。dockerで機械学習 with anaconda(3)
https://qiita.com/kaizen_nagoya/items/483ae708c71c88419c32

「仕事ではじめる機械学習」有賀康顕、中山心太、西林孝　著。dockerで機械学習 with anaconda(4)
https://qiita.com/kaizen_nagoya/items/05a12ced76632561a1d1

「はじめてのPython AIプログラミング」金城俊哉 著。dockerで機械学習 with anaconda(5)
https://qiita.com/kaizen_nagoya/items/d374bfe9366a39eca337

「 scikit-learnとTensorFlowによる実践機械学習」Aurélien Géron著。dockerで機械学習 with anaconda(6)
https://qiita.com/kaizen_nagoya/items/140428dfce7e3234ceb7

「詳解　ディープラーニング　TensorFlow・Kerasによる時系列データ処理」巣籠悠輔　著。dockerで機械学習 with anaconda(7)
https://qiita.com/kaizen_nagoya/items/244a981c9160c0d50a0e

「実践機械学習システム」Willi Richest, Luis Pedro Coelho著。dockerで機械学習 with anaconda(8)
https://qiita.com/kaizen_nagoya/items/1132e52ef6407637c47b

「pythonではじめる機械学習」Andreas C. Muller, Sarah Guido著。dockerで機械学習 with anaconda(9)
https://qiita.com/kaizen_nagoya/items/0960a286b61d50381925

「実践 Deep Learning ――PythonとTensorFlowで学ぶ次世代の機械学習アルゴリズム」Nikhil Buduma著。dockerで機械学習(10) with anaconda(10)
https://qiita.com/kaizen_nagoya/items/8b8811e8b35d7295bb14

dockerで機械学習(11) with anaconda(11)「［第2版］Python機械学習プログラミング 達人データサイエンティストによる理論と実践」Sebastian Raschka, Vahid Mirjalili 著
https://qiita.com/kaizen_nagoya/items/619335d11203d0f04797

dockerで機械学習(12) with anaconda(12)「Deep Learning 深層学習」Ian Goodfellow, Yoshua Bengio, Aaron Courville 著
https://qiita.com/kaizen_nagoya/items/8645c9a94d8f1b1a0fd1

dockerで機械学習(13) with anaconda(13)カラー図解　Raspberry pi ではじめる機械学習　基礎からディープラーニングまで
https://qiita.com/kaizen_nagoya/items/f8e4c20ffea772e15c0b

dockerで機械学習(14) with anaconda(14)「Feature Engineering for Machine Learning」Alice Zheng 著
https://qiita.com/kaizen_nagoya/items/49354b956f0e6750d8e9

dockerで機械学習(15) with anaconda(15)「Deep Learning Cookbook Practical Recipes to Get Started Quickly」Douwe Osinga 著
https://qiita.com/kaizen_nagoya/items/966c463150a854749922

dockerで機械学習(16) with anaconda(16)「Deep Learning Essentials」 Wei Di, Anurag Bhardwaj, Jianing Wei 著
https://qiita.com/kaizen_nagoya/items/ab4442b88329a2a377e4

dockerで機械学習(17) with anaconda(17)「PythonとKerasによるディープラーニング」 ：Francois Chollet著
https://qiita.com/kaizen_nagoya/items/bce4fa73560370733ea2

dockerで機械学習(18) with anaconda(18)「Deep Learning with Keras」 Antonio Gulli, Sujit Pal著
https://qiita.com/kaizen_nagoya/items/3bdeed004c38e3922b82

dockerで機械学習(19) with anaconda(19)「Deep Learning Quick Reference」 Mike Bernico著
https://qiita.com/kaizen_nagoya/items/22d8a36340cab0035adc

dockerで機械学習(20) with anaconda(20)「Data Science in the Cloud with Microsoft Azure Machine Learning and R」Stephen Elston 著
https://qiita.com/kaizen_nagoya/items/43e1a9d74bec907297b3

Azureとうまく接続できていません。未完です。

dockerで機械学習(21) with anaconda(21)「Applied Text Analysis with Python」 By Benjamin Bengfort, Tony Ojeda, Rebecca Bilbro
https://qiita.com/kaizen_nagoya/items/715231d2e587f2ba34ee

dockerで機械学習(22) with anaconda(22)「Deep Learning for Computer Vision」 By Rajalingappaa Shanmugamani
https://qiita.com/kaizen_nagoya/items/bf3bf3d22515c1d5b2ad

dockerで機械学習(23) with anaconda(23)「Deep Learning with PyTorch」By Vishnu Subramanian
https://qiita.com/kaizen_nagoya/items/77d6ee15edd7d6d06470

dockerで機械学習(24) with anaconda(24)「Machine Learning with Python Cookbook」 By Chris Albon
https://qiita.com/kaizen_nagoya/items/b2c6801d029a58692285

dockerで機械学習(25) with anaconda(25)「Mastering TensorFlow 1.x」By Armando Fandango
https://qiita.com/kaizen_nagoya/items/62a95ea4958198752e78

dockerで機械学習(26) with anaconda(26)「Natural Language Processing with PyTorch」By Delip Rao
https://qiita.com/kaizen_nagoya/items/db46e0f162fa07ec4a30

dockerで機械学習(27) with anaconda(27)「Practical Convolutional Neural Networks」By Md. Karim, Mohit Sewak, Pradeep Pujari
https://qiita.com/kaizen_nagoya/items/3ecf991aec86d81c93ef

dockerで機械学習(28) with anaconda(28)「Feature Engineering for Machine Learning」 By Alice Zheng, Amanda Casari
https://qiita.com/kaizen_nagoya/items/69fcf81f185881a954c4

dockerで機械学習(29) with anaconda(29)「Python Deep Learning」 By Valentino Zocca, Gianmario Spacagna, Daniel Slater, Peter Roelants
https://qiita.com/kaizen_nagoya/items/fe18adf6a2e47133b9b0

dockerで機械学習(30) with anaconda(30)「Advanced Deep Learning with Keras」 By Philippe Remy
https://qiita.com/kaizen_nagoya/items/50aadb404ea67abde623

dockerで機械学習(31) with anaconda(31)「Fundamentals of Deep Learning」 By Nikhil Buduma
https://qiita.com/kaizen_nagoya/items/4d9e037aef317b00be10

dockerで機械学習(32) with anaconda(32)「Hands-On Deep Learning with TensorFlow 」By Dan Van Boxel
https://qiita.com/kaizen_nagoya/items/d7200abcdac6b24bc23f

dockerで機械学習(33) with anaconda(33)「Deep Learning with Theano 」By Christopher Bourez
https://qiita.com/kaizen_nagoya/items/e7ea0fde7ba68645b63e

dockerで機械学習(34) with anaconda(34)「Python Deep Learning Cookbook」 By Indra Bakker
https://qiita.com/kaizen_nagoya/items/c4397366e377e75d5636

dockerで機械学習(35) with anaconda(35)「scikit-learn Cookbook」 2nd Edition By Trent Hauck, Julian Avila
https://qiita.com/kaizen_nagoya/items/03867dee08bc35cc5a75

dockerで機械学習(36) with anaconda(36)「Learning TensorFlow」 By Itay Lieder, Yehezkel Resheff, Tom Hope
https://qiita.com/kaizen_nagoya/items/9cd8772eea64f4d4cd06

dockerで機械学習(37) with anaconda(37)「Natural Language Processing with Python Cookbook」 By Pratap Dangeti, Krishna Bhavsar, Naresh Kumar
https://qiita.com/kaizen_nagoya/items/3c36476deddd4a63e6ab

dockerで機械学習(38) with anaconda(38)「Mastering Machine Learning with scikit-learn」2nd Edition By Gavin Hackeling
https://qiita.com/kaizen_nagoya/items/6414d7b66eeb1eba5376

dockerで機械学習(39) with anaconda(39)「Thoughtful Machine Learning with Python」 By Matthew Kirk
https://qiita.com/kaizen_nagoya/items/e98c9c1654df3a3bffce

dockerで機械学習(40) with anaconda(40)「Hands-On Data Science and Python Machine Learning」By Frank Kane
https://qiita.com/kaizen_nagoya/items/d7bc5f31d9bcffd07e82

dockerで機械学習(41) with anaconda(41)「Machine Learning and Security」 By Clarence Chio, David Freeman
https://qiita.com/kaizen_nagoya/items/83bcb2ae084764c3bc39

## with R
dockerで機械学習(71) with R (1)「入門 機械学習」Drew Conway, John Myles White 著
https://qiita.com/kaizen_nagoya/items/e3722c04ae35e82ecca2

dockerで機械学習(72) with R (2)「データサイエンスのための統計学入門 ―予測、分類、統計モデリング、統計的機械学習とRプログラミング」Peter Bruce、Andrew Bruce　著
https://qiita.com/kaizen_nagoya/items/479e3283a2d030726254

dockerで機械学習(73) with R (3)「RとKerasによるディープラーニング」François Chollet、J. J. Allaire　著
https://qiita.com/kaizen_nagoya/items/57b0d84b3ce4f754485d

dockerで機械学習(74) with R (4)Introduction to Machine Learning with R By Scott Burger
https://qiita.com/kaizen_nagoya/items/be23896636af7a7b014d
 
dockerで機械学習(75) with R(5)「R Deep Learning Cookbook」 By Philippe Remy
https://qiita.com/kaizen_nagoya/items/4d6d4b5d9739bcffbf02

dockerで機械学習(76) with R (6)「Mastering Machine Learning with R 」By Cory Lesmeister
https://qiita.com/kaizen_nagoya/items/c3d51cdd3b811dac4d26

「「Rによる機械学習」の勉強履歴（1）」後追い: dockerで機械学習(77) with R (7)
https://qiita.com/kaizen_nagoya/items/68170a86b1b3dd5e596b

Machine-Learning-with-R-Cookbook-Second-Edition-master:dockerで機械学習(78) with R (8)
https://qiita.com/kaizen_nagoya/items/cbbed4d49ebb9c479816

「R Deep Learning Cookbook」 By Philippe Remy dockerで機械学習(79)AI(66)
https://qiita.com/kaizen_nagoya/items/4d6d4b5d9739bcffbf02

## other languages
dockerで機械学習(81) with scala(1)「Scala Machine Learning Projects 」By Md. Karim
https://qiita.com/kaizen_nagoya/items/6498af33ace4e50b48dd

dockerで機械学習(82) with swift(1)「Machine Learning with Swift」By Alexander Sosnovshchenko
https://qiita.com/kaizen_nagoya/items/7a85d48841d9150448a2

dockerで機械学習(83) with Hadoop (1)「Deep Learning with Hadoop」By Dipayan Dev
https://qiita.com/kaizen_nagoya/items/fd4fb931d029e3308038

dockerで機械学習(84) with scala(3)「Scala for Machine Learning」 2nd Edition By Patrick Nicolas
https://qiita.com/kaizen_nagoya/items/2024594040a691f5a0e0

dockerで機械学習(85) with Go(1)「Machine Learning With Go」 By Daniel Whitenack
https://qiita.com/kaizen_nagoya/items/842e83f3da652d9f3acc

dockerで機械学習(86) with Spark(1)「Machine Learning with Spark」 By Rajdeep Dua, Manpreet Singh Ghotra, Nick Pentreath
https://qiita.com/kaizen_nagoya/items/d2fdfdf24effe5a76977

dockerで機械学習(87) with JAVA(1)「Machine Learning: End-to-End guide for Java developers」 By Richard Reese, Jennifer Reese, Bostjan Kaluza, Uday Kamath, Krishna Choppella
https://qiita.com/kaizen_nagoya/items/2d3a4f168b4c9a28b32e

## 環境構築
dockerで機械学習(101) 環境構築(1) docker どっかーら、どーやってもエラーばっかり。
https://qiita.com/kaizen_nagoya/items/690d806a4760d9b9e040

dockerで機械学習(102) 環境構築(2) Docker for Windows
https://qiita.com/kaizen_nagoya/items/c4daa5cf52e9f0c2c002

dockerで機械学習(103) 環境構築(3) docker/linux/macos bash スクリプト, ms-dos batchファイル
https://qiita.com/kaizen_nagoya/items/3f7b39110b7f303a5558

dockerで機械学習(104) 環境構築(4) R 難関いくつ？
https://qiita.com/kaizen_nagoya/items/5fb44773bc38574bcf1c

dockerで機械学習(105)環境構築(5)docker関連ファイルの管理
https://qiita.com/kaizen_nagoya/items/4f03df9a42c923087b5d

# 当面の方針
下記の候補から、githubなどでソースコードを公開しているものから実行する。

下記候補は、oreilly
http://shop.oreilly.com
で、「Deep Learning」「Machine Learning」で検索した本で100冊以上一覧にした。

## 候補
### 2019 
20191105追記

Programming PyTorch for Deep Learning
By Ian Pointer
Publisher: O'Reilly Media
Release Date: September 2019

Deep Learning from Scratch
By Seth Weidman
Publisher: O'Reilly Media
Release Date: September 2019

Practical Deep Learning for Cloud, Mobile, and Edge
By Anirudh Koul, Siddha Ganju, Meher Kasam
Publisher: O'Reilly Media
Release Date: October 2019

Deep Learning for the Life Sciences
By Bharath Ramsundar, Peter Eastman, Vijay Pande, Patrick Walters
Publisher: O'Reilly Media
Release Date: April 2019

Generative Deep Learning
By David Foster
Publisher: O'Reilly Media
Release Date: July 2019

Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow, 2nd Edition
By Aurélien Géron
Publisher: O'Reilly Media
Release Date: September 2019

Practical Automated Machine Learning on Azure
By Wee Hyong Tok, Deepak Mukunthu, Parashar Shah
Publisher: O'Reilly Media
Release Date: September 2019

Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow, 2nd Edition
By Aurélien Géron
Publisher: O'Reilly Media
Release Date: September 2019

Machine Learning Pocket Reference
By Matt Harrison
Publisher: O'Reilly Media
Release Date: August 2019

### 2018
(16)
Deep Learning Essentials 
By Wei Di, Anurag Bhardwaj, Jianing Wei
Packt Publishing, January 2018
http://shop.oreilly.com/product/9781785880360.do

Deep Learning By Example
By Ahmed Menshawy
Publisher: Packt Publishing
Release Date: February 2018
http://shop.oreilly.com/product/9781788399906.do

TensorFlow for Deep Learning
By Reza Zadeh, Bharath Ramsundar
Publisher: O'Reilly Media
Release Date: March 2018
http://shop.oreilly.com/product/0636920065869.do

(18) https://qiita.com/kaizen_nagoya/items/3bdeed004c38e3922b82
Deep Learning with Keras
By Antonio Gulli, Sujit Pal
Publisher: Packt Publishing
Release Date: January 2018
http://shop.oreilly.com/product/0636920163886.do

(19)
Deep Learning Quick Reference
By Mike Bernico
Publisher: Packt Publishing
Release Date: March 2018
http://shop.oreilly.com/product/9781788837996.do

Keras Deep Learning Projects
By Tsvetoslav Tsekov
Publisher: Packt Publishing
Release Date: January 2018
http://shop.oreilly.com/product/0636920164494.do


R Deep Learning Projects
By Yuxi Liu, Pablo Maldonado
Publisher: Packt Publishing
Release Date: February 2018
https://ssearch.oreilly.com/?i=1;page=2;q=Deep+Learning&act=pg_2

R Deep Learning Solutions
By Dr. PKS Prakash
Publisher: Packt Publishing
Release Date: February 2018
http://shop.oreilly.com/product/0636920171614.do

(21)
Applied Text Analysis with Python
Enabling Language-Aware Data Products with Machine Learning
By Benjamin Bengfort, Tony Ojeda, Rebecca Bilbro
Publisher: O'Reilly Media
Release Date: June 2018
http://shop.oreilly.com/product/0636920052555.do

Machine Learning for Text
Mar 20, 2018
by Charu C. Aggarwal
https://www.amazon.com/Machine-Learning-Text-Charu-Aggarwal/dp/3319735306/ref=sr_1_6?ie=UTF8&qid=1539737958&sr=8-6&keywords=Deep+Learning+with+Text

(22)
Deep Learning for Computer Vision
By Rajalingappaa Shanmugamani
Publisher: Packt Publishing
Release Date: January 2018
http://shop.oreilly.com/product/9781788295628.do

(23)
Deep Learning with PyTorch
By Vishnu Subramanian
Publisher: Packt Publishing
Release Date: February 2018
http://shop.oreilly.com/product/9781788624336.do

(81)
Scala Machine Learning Projects
By Md. Karim
Publisher: Packt Publishing
Release Date: January 2018
http://shop.oreilly.com/product/9781788479042.do

(24)
Machine Learning with Python Cookbook
By Chris Albon
Publisher: O'Reilly Media
Release Date: March 2018
http://shop.oreilly.com/product/0636920085423.do

(25)
Mastering TensorFlow 1.x
By Armando Fandango
Publisher: Packt Publishing
Release Date: January 2018
http://shop.oreilly.com/product/9781788292061.do

(26)
Natural Language Processing with PyTorch
By Delip Rao
Publisher: O'Reilly Media
Release Date: July 2018
http://shop.oreilly.com/product/0636920063445.do

(27)
Practical Convolutional Neural Networks
By Md. Karim, Mohit Sewak, Pradeep Pujari
Publisher: Packt Publishing
Release Date: February 2018
http://shop.oreilly.com/product/9781788392303.do

(74)
Introduction to Machine Learning with R
By Scott Burger
Publisher: O'Reilly Media
Release Date: March 2018
http://shop.oreilly.com/product/0636920058885.do

Machine Learning – kurz & gut
Eine Einführung mit Python, Pandas und Scikit-Learn
By Oliver Zeigermann, Chi Nhan Nguyen
Publisher: O'Reilly Verlag via dpunkt
Release Date: April 2018
http://shop.oreilly.com/product/9783960090526.do

(82)
Machine Learning with Swift
By Alexander Sosnovshchenko
Publisher: Packt Publishing
Release Date: February 2018
http://shop.oreilly.com/product/9781787121515.do

(28)
Feature Engineering for Machine Learning
By Alice Zheng, Amanda Casari
Publisher: O'Reilly Media
Release Date: March 2018
http://shop.oreilly.com/product/0636920049081.do


### 2017
(3)https://qiita.com/kaizen_nagoya/items/483ae708c71c88419c32
Deep Learning with Keras
By Antonio Gulli, Sujit Pal
Publisher: Packt Publishing
Release Date: April 2017
http://shop.oreilly.com/product/9781787128422.do

(29) https://qiita.com/kaizen_nagoya/items/fe18adf6a2e47133b9b0
Python Deep Learning
By Valentino Zocca, Gianmario Spacagna, Daniel Slater, Peter Roelants
Publisher: Packt Publishing
Release Date: April 2017
http://shop.oreilly.com/product/9781786464453.do

Getting Started with Java Deep Learning
By Sercan Karaoglu
Publisher: Packt Publishing
Release Date: February 24, 2017
http://shop.oreilly.com/product/0636920078791.do

Tensorflow Deep Learning Solutions for Images
By Will Ballard
Publisher: Packt Publishing
Release Date: October 2017
http://shop.oreilly.com/product/0636920128090.do

(83) https://qiita.com/kaizen_nagoya/items/fd4fb931d029e3308038
Deep Learning with Hadoop
By Dipayan Dev
Publisher: Packt Publishing
Release Date: February 2017
http://shop.oreilly.com/product/9781787124769.do

Deep Learning with TensorFlow
By Giancarlo Zaccone, Md. Rezaul Karim, Ahmed Menshawy
Publisher: Packt Publishing
Release Date: April 2017
http://shop.oreilly.com/product/9781786469786.do

Deep Learning with R
By Vincenzo Lomonaco
Publisher: Packt Publishing
Release Date: March 28, 2017
https://ssearch.oreilly.com/?i=1;page=2;q=Deep+Learning&act=pg_2

(30) https://qiita.com/kaizen_nagoya/items/50aadb404ea67abde623
Advanced Deep Learning with Keras
By Philippe Remy
Publisher: Packt Publishing
Release Date: December 2017
http://shop.oreilly.com/product/0636920154891.do

(75)
R Deep Learning Cookbook
By PKS Prakash, Achyutuni Rao
Publisher: Packt Publishing
Release Date: August 2017
http://shop.oreilly.com/product/9781787121089.do

(31) https://qiita.com/kaizen_nagoya/items/4d9e037aef317b00be10
Fundamentals of Deep Learning
By Nikhil Buduma
Publisher: O'Reilly Media
Release Date: May 2017
http://shop.oreilly.com/product/0636920039709.do

(32) https://qiita.com/kaizen_nagoya/items/d7200abcdac6b24bc23f
Hands-On Deep Learning with TensorFlow
By Dan Van Boxel
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781787282773.do

(33) https://qiita.com/kaizen_nagoya/items/e7ea0fde7ba68645b63e
Deep Learning with Theano
By Christopher Bourez
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781786465825.do

(34) https://qiita.com/kaizen_nagoya/items/c4397366e377e75d5636
Python Deep Learning Cookbook
By Indra Bakker
Publisher: Packt Publishing
Release Date: October 2017
http://shop.oreilly.com/product/9781787125193.do

Deep Learning: Practical Neural Networks with Java
By Bostjan Kaluza, Alan Souza, Fabio Soares, Yusuke Sugomori
Publisher: Packt Publishing
Release Date: June 2017
http://shop.oreilly.com/product/9781788470315.do

TensorFlow 1.x Deep Learning Cookbook
By Antonio Gulli, Amita Kapoor
Publisher: Packt Publishing
Release Date: December 2017
http://shop.oreilly.com/product/9781788293594.do

(35) https://qiita.com/kaizen_nagoya/items/03867dee08bc35cc5a75
scikit-learn Cookbook, 2nd Edition
By Trent Hauck, Julian Avila
Publisher: Packt Publishing
Release Date: November 2017
http://shop.oreilly.com/product/9781787286382.do

(11) https://qiita.com/kaizen_nagoya/items/619335d11203d0f04797
Python Machine Learning, 2nd Edition
By Sebastian Raschka, Vahid Mirjalili
Publisher: Packt Publishing
Release Date: September 2017
http://shop.oreilly.com/product/9781787125933.do

(6) https://qiita.com/kaizen_nagoya/items/140428dfce7e3234ceb7
Hands-On Machine Learning with Scikit-Learn and TensorFlow
By Aurélien Géron
Publisher: O'Reilly Media
Release Date: March 2017
http://shop.oreilly.com/product/0636920052289.do

(36) https://qiita.com/kaizen_nagoya/items/9cd8772eea64f4d4cd06
Learning TensorFlow
By Itay Lieder, Yehezkel Resheff, Tom Hope
Publisher: O'Reilly Media
Release Date: August 2017
http://shop.oreilly.com/product/0636920063698.do

Predictive Analytics with TensorFlow
By Md. Karim
Publisher: Packt Publishing
Release Date: November 2017
http://shop.oreilly.com/product/9781788398923.do

(37)
Natural Language Processing with Python Cookbook
By Pratap Dangeti, Krishna Bhavsar, Naresh Kumar
Publisher: Packt Publishing
Release Date: November 2017
http://shop.oreilly.com/product/9781787289321.do

Machine Learning & Data Science Landscape
By Christina Voskoglou, Mark Wilcox, Stijn Schuermans
Publisher: VisionMobile
Release Date: March 2017
http://shop.oreilly.com/product/0636920114277.do

(38)
Mastering Machine Learning with scikit-learn, 2nd Edition
By Gavin Hackeling
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781788299879.do

(39) https://qiita.com/kaizen_nagoya/items/e98c9c1654df3a3bffce
Thoughtful Machine Learning with Python
By Matthew Kirk
Publisher: O'Reilly Media
Release Date: January 2017
http://shop.oreilly.com/product/0636920039082.do

(84)
Scala for Machine Learning, 2nd Edition
By Patrick Nicolas
Publisher: Packt Publishing
Release Date: September 2017
http://shop.oreilly.com/product/9781787122383.do

(85)
Machine Learning With Go
By Daniel Whitenack
Publisher: Packt Publishing
Release Date: September 2017
http://shop.oreilly.com/product/9781785882104.do

Machine Learning Algorithms
By Giuseppe Bonaccorso
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781785889622.do

(86)
Machine Learning with Spark
By Rajdeep Dua, Manpreet Singh Ghotra, Nick Pentreath
Publisher: Packt Publishing
Release Date: April 2017
http://shop.oreilly.com/product/9781785889936.do

Machine Learning with TensorFlow 1.x
By Quan Hua, Shams Azeem, Saif Ahmed
Publisher: Packt Publishing
Release Date: November 2017
http://shop.oreilly.com/product/9781786462961.do

(40)
Hands-On Data Science and Python Machine Learning
By Frank Kane
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781787280748.do

(76)
Mastering Machine Learning with R
By Cory Lesmeister
Publisher: Packt Publishing
Release Date: April 2017
http://shop.oreilly.com/product/9781787287471.do

(87)
Machine Learning: End-to-End guide for Java developers
By Richard Reese, Jennifer Reese, Bostjan Kaluza, Uday Kamath, Krishna Choppella
Publisher: Packt Publishing
Release Date: October 2017
http://shop.oreilly.com/product/9781788622219.do

Machine Learning and Security
By Clarence Chio, David Freeman
Publisher: O'Reilly Media
Release Date: October 2017
http://shop.oreilly.com/product/0636920065555.do

Python Natural Language Processing
By Jalaj Thanaki
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781787121423.do

Effective Amazon Machine Learning
By Alexis Perrier
Publisher: Packt Publishing
Release Date: April 2017
http://shop.oreilly.com/product/9781785883231.do

Learn more Machine Learning for Developers
Machine Learning for Developers
By Rodolfo Bonnin
Publisher: Packt Publishing
Release Date: October 2017
http://shop.oreilly.com/product/9781786469878.do


Mastering Java Machine Learning
By Uday Kamath, Krishna Choppella
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781785880513.do

Apache Spark 2.x Machine Learning Cookbook
By Siamak Amirghodsi, Meenakshi Rajendran, Broderick Hall, Shuen Mei
Publisher: Packt Publishing
Release Date: September 2017
http://shop.oreilly.com/product/9781783551606.do

Learn more Python Machine Learning By Example
Python Machine Learning By Example
By Yuxi Liu
Publisher: Packt Publishing
Release Date: May 2017
http://shop.oreilly.com/product/9781783553112.do

Machine Learning for OpenCV
By Michael Beyeler
Publisher: Packt Publishing
Release Date: July 2017
http://shop.oreilly.com/product/9781783980284.do

Mastering Machine Learning with Spark 2.x
By Alex Tellez, Max Pumperla, Michal Malohlava
Publisher: Packt Publishing
Release Date: August 2017
http://shop.oreilly.com/product/9781785283451.do

### 2016
Java Deep Learning Essentials
By Yusuke Sugomori
Publisher: Packt Publishing
Release Date: May 2016
http://shop.oreilly.com/product/9781785282195.do

Deep Learning with Python
By Eder Santana
Publisher: Packt Publishing
Release Date: February 29, 2016
http://shop.oreilly.com/product/0636920051237.do

Deep Learning with TensorFlow
By Dan Van Boxel
Publisher: Packt Publishing
Release Date: June 27, 2016
http://shop.oreilly.com/product/0636920055044.do

Python: Deeper Insights into Machine Learning
By Sebastian Raschka, David Julian, John Hearty
Publisher: Packt Publishing
Release Date: August 2016
http://shop.oreilly.com/product/9781787128576.do

Advanced Machine Learning with Python
By John Hearty
Publisher: Packt Publishing
Release Date: July 2016
http://shop.oreilly.com/product/9781784398637.do

Practical Machine Learning with H2O
By Darren Cook
Publisher: O'Reilly Media
Release Date: December 2016
http://shop.oreilly.com/product/0636920053170.do

Mastering Data Mining with Python – Find patterns hidden in your data
By Megan Squire
Publisher: Packt Publishing
Release Date: August 2016
http://shop.oreilly.com/product/9781785889950.do

Machine Learning For Dummies
By John Paul Mueller, Luca Massaron
Publisher: Wiley / For Dummies
Release Date: May 2016
http://shop.oreilly.com/product/9781119245513.do

Machine Learning in Java
By Bostjan Kaluza
Publisher: Packt Publishing
Release Date: April 2016
http://shop.oreilly.com/product/9781784396589.do

Designing Machine Learning Systems with Python
By David Julian
Publisher: Packt Publishing
Release Date: April 2016
http://shop.oreilly.com/product/9781785882951.do

Python Machine Learning Blueprints: Intuitive data projects you can relate to
By Alexander T. Combs
Publisher: Packt Publishing
Release Date: July 2016
http://shop.oreilly.com/product/9781784394752.do

Large Scale Machine Learning with Python
By Bastiaan Sjardin, Luca Massaron, Alberto Boschetti
Publisher: Packt Publishing
Release Date: August 2016
http://shop.oreilly.com/product/9781785887215.do

R: Unleash Machine Learning Techniques
By Raghav Bali, Dipanjan Sarkar, Brett Lantz, Cory Lesmeister
Publisher: Packt Publishing
Release Date: October 2016
http://shop.oreilly.com/product/9781787127340.do

R: Recipes for Analysis, Visualization and Machine Learning
By Viswa Viswanathan, Shanthi Viswanathan, Atmajitsinh Gohil, Yu-Wei, Chiu
Publisher: Packt Publishing
Release Date: November 2016
http://shop.oreilly.com/product/9781787289598.do

R Machine Learning By Example
By Raghav Bali, Dipanjan Sarkar
Publisher: Packt Publishing
Release Date: March 2016
http://shop.oreilly.com/product/9781784390846.do

Practical Machine Learning
By Sunila Gollapudi
Publisher: Packt Publishing
Release Date: January 2016
http://shop.oreilly.com/product/9781784399689.do

Large Scale Machine Learning with Spark
By Md. Rezaul Karim, Md. Mahedi Kaysar
Publisher: Packt Publishing
Release Date: October 2016
http://shop.oreilly.com/product/9781785888748.do

Mastering .NET Machine Learning
By Jamie Dixon
Publisher: Packt Publishing
Release Date: March 2016
http://shop.oreilly.com/product/9781785888403.do

Introduction to Machine Learning with Python
By Andreas C. Müller, Sarah Guido
Publisher: O'Reilly Media
Release Date: September 2016
http://shop.oreilly.com/product/0636920030515.do

Python: Real World Machine Learning
By Prateek Joshi, John Hearty, Bastiaan Sjardin, Luca Massaron, Alberto Boschetti
Publisher: Packt Publishing
Release Date: November 2016
http://shop.oreilly.com/product/9781787123212.do

F# for Machine Learning Essentials
By Sudipta Mukherjee
Publisher: Packt Publishing
Release Date: February 2016
http://shop.oreilly.com/product/9781783989348.do

Apache Spark Machine Learning Blueprints
By Alex Liu
Publisher: Packt Publishing
Release Date: May 2016
http://shop.oreilly.com/product/9781785880391.do

Learn more Machine Learning for the Web
Machine Learning for the Web
By Andrea Isoni
Publisher: Packt Publishing
Release Date: July 2016
http://shop.oreilly.com/product/9781785886607.do

Learn more Python Machine Learning Cookbook
Python Machine Learning Cookbook
By Prateek Joshi
Publisher: Packt Publishing
Release Date: June 2016
http://shop.oreilly.com/product/9781786464477.do

### 2015
Deep Learning
By O'Reilly Media, Inc.
Publisher: O'Reilly Media
Release Date: June 16, 2015
http://shop.oreilly.com/product/0636920041924.do

Python Machine Learning
By Sebastian Raschka
Publisher: Packt Publishing
Release Date: September 2015
http://shop.oreilly.com/product/9781783555130.do

Learn more Learning Apache Kafka
Learning Apache Kafka
By Nishant Garg
Publisher: Packt Publishing
Release Date: February 2015
http://shop.oreilly.com/product/9781784393090.do

Building Machine Learning Systems with Python
By Luis Pedro Coelho, Willi Richert
Publisher: Packt Publishing
Release Date: March 2015
http://shop.oreilly.com/product/9781784392772.do

Learning YARN
By Akhil Arora, Shrey Mehrotra
Publisher: Packt Publishing
Release Date: August 2015
http://shop.oreilly.com/product/9781784393960.do

Evaluating Machine Learning Models
By Alice Zheng
Publisher: O'Reilly Media
Release Date: September 08, 2015
https://www.oreilly.com/data/free/evaluating-machine-learning-models.csp

Data Science in the Cloud with Microsoft Azure Machine Learning and R
By Stephen Elston
Publisher: O'Reilly Media
Release Date: February 27, 2015
https://www.oreilly.com/data/free/data-science-in-the-cloud.csp

Machine Learning in Python
By Michael Bowles
Publisher: Wiley
Release Date: March 2015
http://shop.oreilly.com/product/9781118961742.do

Introduction to Statistical Machine Learning
By Masashi Sugiyama
Publisher: Elsevier / Morgan Kaufmann
Release Date: October 2015
http://shop.oreilly.com/product/9780128021217.do

Mastering Machine Learning with R
By Cory Lesmeister
Publisher: Packt Publishing
Release Date: October 2015
http://shop.oreilly.com/product/9781783984527.do

Building Machine Learning Systems with Python
By Luis Pedro Coelho, Willi Richert
Publisher: Packt Publishing
Release Date: March 2015
http://shop.oreilly.com/product/9781784392772.do

Microsoft Azure Machine Learning
By Sumit Mund
Publisher: Packt Publishing
Release Date: June 2015
http://shop.oreilly.com/product/9781784390792.do

Machine Learning with R
By Brett Lantz
Publisher: Packt Publishing
Release Date: July 2015
http://shop.oreilly.com/product/9781784393908.do

Learn more Test-Driven Machine Learning
Test-Driven Machine Learning
By Justin Bozonier
Publisher: Packt Publishing
Release Date: November 2015
http://shop.oreilly.com/product/9781784399085.do

## 2014
Machine Learning
By Jason Bell
Publisher: Wiley
Release Date: October 2014
http://shop.oreilly.com/product/9781118889060.do

R Machine Learning Essentials
By Michele Usuelli
Publisher: Packt Publishing
Release Date: November 2014
http://shop.oreilly.com/product/9781783987740.do

Thoughtful Machine Learning
By Matthew Kirk
Publisher: O'Reilly Media
Release Date: September 2014
http://shop.oreilly.com/product/0636920032298.do

Clojure for Machine Learning
By Akhil Wali
Publisher: Packt Publishing
Release Date: April 2014
http://shop.oreilly.com/product/9781783284351.do

Machine Learning
By Yves Kodratoff, Ryszard S. Michalski
Publisher: Elsevier / Morgan Kaufmann
Release Date: June 2014
http://shop.oreilly.com/product/9781558601192.do

Proceedings of the Fourth International Workshop on MACHINE LEARNING
By Pat Langley
Publisher: Elsevier / Morgan Kaufmann
Release Date: May 2014
http://shop.oreilly.com/product/9780934613415.do

Machine Learning
By Ryszard S. Michalski, Jaime G. Carbonell, Tom M. Mitchell
Publisher: Elsevier / Morgan Kaufmann
Release Date: June 2014
http://shop.oreilly.com/product/9780934613095.do

Mastering Machine Learning with scikit-learn
By Gavin Hackeling
Publisher: Packt Publishing
Release Date: October 2014
http://shop.oreilly.com/product/9781783988365.do

Practical Machine Learning: Innovations in Recommendation
By Ted Dunning, Ellen Friedman
Publisher: O'Reilly Media
Release Date: April 2014
http://shop.oreilly.com/product/0636920033172.do

Practical Machine Learning: A New Look at Anomaly Detection
By Ted Dunning, Ellen Friedman
Publisher: O'Reilly Media
Release Date: July 2014
http://shop.oreilly.com/product/0636920034650.do

Machine Learning Methods for Planning
By Steven Minton
Publisher: Elsevier / Morgan Kaufmann
Release Date: May 2014
http://shop.oreilly.com/product/9781558602489.do

Conformal Prediction for Reliable Machine Learning
By Vineeth Balasubramanian, Shen-Shyang Ho, Vladimir Vovk
Publisher: Elsevier / Morgan Kaufmann
Release Date: April 2014
http://shop.oreilly.com/product/9780123985378.do

Scala for Machine Learning
By Patrick R. Nicolas
Publisher: Packt Publishing
Release Date: December 2014
http://shop.oreilly.com/product/9781783558742.do

## 2013
Learning scikit-learn: Machine Learning in Python
By Raúl Garreta, Guillermo Moncecchi
Publisher: Packt Publishing
Release Date: November 2013
http://shop.oreilly.com/product/9781783281930.do

Building Machine Learning Systems with Python
By Willi Richert, Luis Pedro Coelho
Publisher: Packt Publishing
Release Date: July 2013
http://shop.oreilly.com/product/9781782161400.do

Machine Learning with R
By Brett Lantz
Publisher: Packt Publishing
Release Date: October 2013
http://shop.oreilly.com/product/9781782162148.do

## 2012
Machine Learning for Hackers
By Drew Conway, John Myles White
Publisher: O'Reilly Media
Release Date: February 2012
http://shop.oreilly.com/product/0636920018483.do

Natural Language Annotation for Machine Learning
By James Pustejovsky, Amber Stubbs
Publisher: O'Reilly Media
Release Date: October 2012
http://shop.oreilly.com/product/0636920020578.do

## 2011
Data Mining: Practical Machine Learning Tools and Techniques
By Ian H. Witten, Eibe Frank, Mark A. Hall
Publisher: Elsevier / Morgan Kaufmann
Release Date: February 2011
http://shop.oreilly.com/product/9780123748560.do

Real World Applications Panel: Machine Learning and Decision Support
By Alon Halevy, Jonathan Seidman, Robert Lancaster, Alasdair Allan
Publisher: O'Reilly Media
Release Date: March 2011
http://shop.oreilly.com/product/0636920018780.do

Machine Learning for Email
By Drew Conway, John Myles White
Publisher: O'Reilly Media
Release Date: October 2011
http://shop.oreilly.com/product/0636920022350.do

## docker
dockerを使うのは次の理由によります。

複数人で同じ作業をするのに環境の違いを意識しなくても作業できる。
Windows, Macintosh, LinuxのOSの違いを意識することなく作業できる。
環境設定は得意な人が一人すれば、あとはそれぞれのPCの環境設定の違いを気にせずに作業できる。
作業結果をネットのどこからでも再開することができる。
debian系のapt-get でソフトウェアの導入が楽。

## apt

```shell-session:docker
# apt update
# apt install vim procps apt-utils sudo wget git
```

## anaconda
anacondaの公式配布をpullで取得

docker fileの方がいいのだろうが、pushで保存する予定なため当面はこの方式。

将来的には、docker fileの利用、加工を計画。まず１０種類作ってからかんがえさせてください。

## conda と pipの使い分け
pythonにはpip、その一種であるanacondaにはcondaというソフトウェアの配布方法がある。

condaでうまくいく場合はcondaを使う。

### 例１　pyside(conda)

```
(base) root@9f32435de7a9:/BuildingMachineLearningSystemsWithPython# pip install pyside
Collecting pyside
  Downloading https://files.pythonhosted.org/packages/36/ac/ca31db6f2225844d37a41b10615c3d371587677efd074db29855e7035de6/PySide-1.2.4.tar.gz (9.3MB)
    100% |████████████████████████████████| 9.3MB 3.1MB/s 
Building wheels for collected packages: pyside
  Running setup.py bdist_wheel for pyside ... error
  Complete output from command /opt/conda/bin/python -u -c "import setuptools, tokenize;__file__='/tmp/pip-install-C2aV7L/pyside/setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" bdist_wheel -d /tmp/pip-wheel-pCHj6z --python-tag cp27:
  Removing /tmp/pip-install-C2aV7L/pyside/pyside_package
  running bdist_wheel
  running build
  Python architecture is 64bit
  error: You need the program "make" on your system path to compile PySide.
  
  ----------------------------------------
  Failed building wheel for pyside
  Running setup.py clean for pyside
Failed to build pyside
Installing collected packages: pyside
  Running setup.py install for pyside ... error
    Complete output from command /opt/conda/bin/python -u -c "import setuptools, tokenize;__file__='/tmp/pip-install-C2aV7L/pyside/setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" install --record /tmp/pip-record-9OYnwH/install-record.txt --single-version-externally-managed --compile:
    Removing /tmp/pip-install-C2aV7L/pyside/pyside_package
    running install
    running build
    Python architecture is 64bit
    error: You need the program "make" on your system path to compile PySide.
    
    ----------------------------------------
Command "/opt/conda/bin/python -u -c "import setuptools, tokenize;__file__='/tmp/pip-install-C2aV7L/pyside/setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" install --record /tmp/pip-record-9OYnwH/install-record.txt --single-version-externally-managed --compile" failed with error code 1 in /tmp/pip-install-C2aV7L/pyside/
```
pipでうまくいかなかった。condaで導入。


```
(base) root@9f32435de7a9:/BuildingMachineLearningSystemsWithPython# conda install pyside
Solving environment: done

## Package Plan ##

  environment location: /opt/conda

  added / updated specs: 
    - pyside


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    pyside-1.2.0               |           py27_0         5.6 MB
    shiboken-1.2.1             |           py27_0         894 KB
    ------------------------------------------------------------
                                           Total:         6.5 MB

The following NEW packages will be INSTALLED:

    pyside:   1.2.0-py27_0
    shiboken: 1.2.1-py27_0

Proceed ([y]/n)? y

Downloading and Extracting Packages
pyside-1.2.0         | 5.6 MB    | ###################################################################### | 100% 
shiboken-1.2.1       | 894 KB    | ###################################################################### | 100% 
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
```

### 例2  matplotlib (pipで再導入)

```shell-session:performance_test.py 
(base) root@9f32435de7a9:/BuildingMachineLearningSystemsWithPython/ch01# python performance_test.py 
Normal Python: 0.550648 sec
Naive NumPy: 0.744641 sec
Good NumPy: 0.015985 sec
(base) root@9f32435de7a9:/BuildingMachineLearningSystemsWithPython/ch01# python analyze_webstats.py 
Traceback (most recent call last):
  File "analyze_webstats.py", line 10, in <module>
    import matplotlib.pyplot as plt
  File "/opt/conda/lib/python2.7/site-packages/matplotlib/pyplot.py", line 115, in <module>
    _backend_mod, new_figure_manager, draw_if_interactive, _show = pylab_setup()
  File "/opt/conda/lib/python2.7/site-packages/matplotlib/backends/__init__.py", line 62, in pylab_setup
    [backend_name], 0)
  File "/opt/conda/lib/python2.7/site-packages/matplotlib/backends/backend_qt5agg.py", line 15, in <module>
    from .backend_qt5 import (
  File "/opt/conda/lib/python2.7/site-packages/matplotlib/backends/backend_qt5.py", line 19, in <module>
    import matplotlib.backends.qt_editor.figureoptions as figureoptions
  File "/opt/conda/lib/python2.7/site-packages/matplotlib/backends/qt_editor/figureoptions.py", line 20, in <module>
    import matplotlib.backends.qt_editor.formlayout as formlayout
  File "/opt/conda/lib/python2.7/site-packages/matplotlib/backends/qt_editor/formlayout.py", line 54, in <module>
    from matplotlib.backends.qt_compat import QtGui, QtWidgets, QtCore
  File "/opt/conda/lib/python2.7/site-packages/matplotlib/backends/qt_compat.py", line 158, in <module>
    raise ImportError("Failed to import any qt binding")
ImportError: Failed to import any qt binding
(base) root@9f32435de7a9:/BuildingMachineLearningSystemsWithPython/ch01# conda install tensorflow
Solving environment: done

# All requested packages already installed.
```
「ImportError("Failed to import any qt binding")」
で検索
https://stackoverflow.com/questions/52346254/importerror-failed-to-import-any-qt-binding-python-tensorflow

```
(base) root@9f32435de7a9:/BuildingMachineLearningSystemsWithPython/ch01# pip uninstall matplotlib
Uninstalling matplotlib-2.2.3:
  Would remove:
    /opt/conda/lib/python2.7/site-packages/matplotlib
    /opt/conda/lib/python2.7/site-packages/matplotlib-2.2.3-py2.7.egg-info
    /opt/conda/lib/python2.7/site-packages/pylab.py
Proceed (y/n)? pip install matplotlib
Your response ('pip install matplotlib') was not one of the expected responses: y, n
Proceed (y/n)? y
  Successfully uninstalled matplotlib-2.2.3
(base) root@9f32435de7a9:/BuildingMachineLearningSystemsWithPython/ch01# pip install matplotlib
Collecting matplotlib
  Downloading https://files.pythonhosted.org/packages/59/08/04933377dc4500e3698e93f9113dc3624874e0914f4c85767ecb5b389084/matplotlib-2.2.3-cp27-cp27mu-manylinux1_x86_64.whl (12.6MB)
    100% |████████████████████████████████| 12.6MB 2.3MB/s 
Requirement already satisfied: python-dateutil>=2.1 in /opt/conda/lib/python2.7/site-packages (from matplotlib) (2.7.3)
Requirement already satisfied: subprocess32 in /opt/conda/lib/python2.7/site-packages (from matplotlib) (3.5.2)
Requirement already satisfied: cycler>=0.10 in /opt/conda/lib/python2.7/site-packages (from matplotlib) (0.10.0)
Requirement already satisfied: six>=1.10 in /opt/conda/lib/python2.7/site-packages (from matplotlib) (1.11.0)
Requirement already satisfied: backports.functools-lru-cache in /opt/conda/lib/python2.7/site-packages (from matplotlib) (1.5)
Requirement already satisfied: pytz in /opt/conda/lib/python2.7/site-packages (from matplotlib) (2018.5)
Requirement already satisfied: pyparsing!=2.0.4,!=2.1.2,!=2.1.6,>=2.0.1 in /opt/conda/lib/python2.7/site-packages (from matplotlib) (2.2.0)
Requirement already satisfied: numpy>=1.7.1 in /opt/conda/lib/python2.7/site-packages (from matplotlib) (1.15.1)
Requirement already satisfied: kiwisolver>=1.0.1 in /opt/conda/lib/python2.7/site-packages (from matplotlib) (1.0.1)
Requirement already satisfied: setuptools in /opt/conda/lib/python2.7/site-packages (from kiwisolver>=1.0.1->matplotlib) (40.2.0)
Installing collected packages: matplotlib
Successfully installed matplotlib-2.2.3
```
## git, wget
githubなどにある場合は、gitコマンド、
ftpなどにある場合は、wgetコマンドを使ってプログラム例を取得する。

## run時のport
jupyter notebook, keras boardなどブラウザで閲覧できる方式のソフトは、
docker内ではGuiを起動していないため、dockerを起動したOSのブラウザで閲覧する。
runの際に、portを開く。

## jupiter notebook
jupyter notebookを起動するときには、
「--port=8888 --ip=0.0.0.0 --allow-root」
というおまじないをする。

### port
jupyter notebookを8888で起動していると、同じポートを使っては起動できない。
今は、他のdockerを閉じてから作業している。

```
OgawaKiyoshi-no-MacBook-Pro:~ ogawakiyoshi$ docker run -it -p 8888:8888 kaizenjapan/conda3-amueller
docker: Error response from daemon: driver failed programming external connectivity on endpoint jovial_swirles (2563caeba49b46552c62c84462d1debb5810bd9a2a34c637b7e12a005b74901b): Bind for 0.0.0.0:8888 failed: port is already allocated.
```

## pip

```
(base) root@f19e2f06eabb:/deep-learning-from-scratch-2/ch01# pip install --upgrade pip
Collecting pip
  Downloading https://files.pythonhosted.org/packages/5f/25/e52d3f31441505a5f3af41213346e5b6c221c9e086a166f3703d2ddaf940/pip-18.0-py2.py3-none-any.whl (1.3MB)
    100% |████████████████████████████████| 1.3MB 2.0MB/s 
distributed 1.21.8 requires msgpack, which is not installed.
Installing collected packages: pip
  Found existing installation: pip 10.0.1
    Uninstalling pip-10.0.1:
      Successfully uninstalled pip-10.0.1
Successfully installed pip-18.0
```

# 参考文献(reference)
dockerでpython
https://hub.docker.com/r/continuumio/anaconda3/~/dockerfile/

ローカル環境をよごさずに Jupyter で python コードが動く環境を手軽につくる方法
https://qiita.com/yaiwase/items/3a58313e028315004a56

Anaconda の JupyterLab を Docker で使う
https://qiita.com/ao_log/items/350a3845d49f4b1d7198

## dockerでR
OSXでRのパッケージtidyverseのインストールに詰まった
https://qiita.com/Wisteria30/items/60b1660fc373100a0d6f
R ScriptやR Markdownからinstall.packages()を呼び出す場合はレポジトリを指定しないとエラーになる
https://qiita.com/maech/items/03b9566fb0fe940e1736
Rでtrying to use CRAN without setting a mirrorと言われたら
https://qiita.com/manabuishiirb/items/88fb9d5207e6802da4b7

## github
Adam Gibson
https://github.com/agibsonccc

Umberto Michelucci
https://github.com/michelucci
Sudo

## arxiv
Theory of Deep Learning III: explaining the
non-overfitting puzzle
https://arxiv.org/pdf/1801.00173.pdf

## docker参考資料(docker reference)
個人的に気になっている仮想化技術等に関するメモ
https://qiita.com/tomPlain/items/f5ff596e5d66516c8bf2

## 一覧
物理記事　上位100
https://qiita.com/kaizen_nagoya/items/66e90fe31fbe3facc6ff

量子(0) 計算機, 量子力学 
https://qiita.com/kaizen_nagoya/items/1cd954cb0eed92879fd4

数学関連記事１００
https://qiita.com/kaizen_nagoya/items/d8dadb49a6397e854c6d

言語・文学記事　１００
https://qiita.com/kaizen_nagoya/items/42d58d5ef7fb53c407d6

医工連携関連記事一覧
https://qiita.com/kaizen_nagoya/items/6ab51c12ba51bc260a82

自動車　記事　１００
https://qiita.com/kaizen_nagoya/items/f7f0b9ab36569ad409c5

通信記事１００
https://qiita.com/kaizen_nagoya/items/1d67de5e1cd207b05ef7

日本語（０）一欄
https://qiita.com/kaizen_nagoya/items/7498dcfa3a9ba7fd1e68

英語(0) 一覧
https://qiita.com/kaizen_nagoya/items/680e3f5cbf9430486c7d

転職(0)一覧
https://qiita.com/kaizen_nagoya/items/f77520d378d33451d6fe

仮説（0）一覧（目標100現在40）
https://qiita.com/kaizen_nagoya/items/f000506fe1837b3590df

Qiita(0)Qiita関連記事一覧（自分）
https://qiita.com/kaizen_nagoya/items/58db5fbf036b28e9dfa6

鉄道（０）鉄道のシステム考察はてっちゃんがてつだってくれる
https://qiita.com/kaizen_nagoya/items/26bda595f341a27901a0

安全（0）安全工学シンポジウムに向けて: 21
https://qiita.com/kaizen_nagoya/items/c5d78f3def8195cb2409

一覧の一覧( The directory of directories of mine.) Qiita(100)
https://qiita.com/kaizen_nagoya/items/7eb0e006543886138f39

Ethernet 記事一覧　Ethernet(0)
https://qiita.com/kaizen_nagoya/items/88d35e99f74aefc98794

Wireshark 一覧 wireshark(0)、Ethernet(48) 
https://qiita.com/kaizen_nagoya/items/fbed841f61875c4731d0

線網（Wi-Fi）空中線(antenna)(0) 記事一覧(118/300目標)
https://qiita.com/kaizen_nagoya/items/5e5464ac2b24bd4cd001

OSEK OS設計の基礎　OSEK(100)
https://qiita.com/kaizen_nagoya/items/7528a22a14242d2d58a3

Error一覧 error(0)
https://qiita.com/kaizen_nagoya/items/48b6cbc8d68eae2c42b8

++ Support(0)　
https://qiita.com/kaizen_nagoya/items/8720d26f762369a80514

Coding(0) Rules, C, Secure, MISRA and so on
https://qiita.com/kaizen_nagoya/items/400725644a8a0e90fbb0

プログラマによる、プログラマのための、統計(0)と確率のプログラミングとその後
https://qiita.com/kaizen_nagoya/items/6e9897eb641268766909

なぜdockerで機械学習するか 書籍・ソース一覧作成中 (目標100)
https://qiita.com/kaizen_nagoya/items/ddd12477544bf5ba85e2

言語処理100本ノックをdockerで。python覚えるのに最適。:10+12
https://qiita.com/kaizen_nagoya/items/7e7eb7c543e0c18438c4

プログラムちょい替え（0）一覧:4件
https://qiita.com/kaizen_nagoya/items/296d87ef4bfd516bc394

官公庁・学校・公的団体（NPOを含む）システムの課題、官（０）
https://qiita.com/kaizen_nagoya/items/04ee6eaf7ec13d3af4c3

「はじめての」シリーズ　 ベクタージャパン　
https://qiita.com/kaizen_nagoya/items/2e41634f6e21a3cf74eb

AUTOSAR(0)Qiita記事一覧, OSEK(75)
https://qiita.com/kaizen_nagoya/items/89c07961b59a8754c869

プログラマが知っていると良い「公序良俗」
https://qiita.com/kaizen_nagoya/items/9fe7c0dfac2fbd77a945

LaTeX(0) 一覧　
https://qiita.com/kaizen_nagoya/items/e3f7dafacab58c499792

自動制御、制御工学一覧（０）
https://qiita.com/kaizen_nagoya/items/7767a4e19a6ae1479e6b

Rust(0) 一覧　
https://qiita.com/kaizen_nagoya/items/5e8bb080ba6ca0281927

小川清最終講義、最終講義（再）計画, Ethernet(100) 英語(100) 安全(100)
https://qiita.com/kaizen_nagoya/items/e2df642e3951e35e6a53


大規模言語モデル講座 基礎編 2025 Autumn　敗因を勝因に
https://qiita.com/kaizen_nagoya/items/34ffd2b0c47a5f3665d9

MCP入門 〜面倒なことはAIエージェントにやらせよう〜 by からあげ を聞きながら
https://qiita.com/kaizen_nagoya/items/54b648c838fae8d57e38

MCP入門 〜面倒なことはAIエージェントにやらせよう〜 by からあげ を聞きながら、補足と反論 by ChatGPT
https://qiita.com/kaizen_nagoya/items/0939d58d31666562090c

C言語(C++)が必要な人と必要ない人
https://qiita.com/kaizen_nagoya/items/2afe9e846b55b24cb6f1

C言語(C++)が必要な人、必要ない人　with ChatGPT
https://qiita.com/kaizen_nagoya/items/a074cb8cd292d8d94bd4

C言語を習得する３つの方法
https://qiita.com/kaizen_nagoya/items/84cab0888c193bba429b

C言語を習得する３つの方法　with ChatGPT
https://qiita.com/kaizen_nagoya/items/4a3518a18fa49f46787f

＜この記事は個人の過去の経験に基づく個人の感想です。現在所属する組織、業務とは関係がありません。＞
<This article is an individual impression based on the individual's experience. It has nothing to do with the organization or business to which I currently belong. ＞
### 文書履歴(document history)
ver. 0.10 初稿 20181004
ver. 0.11 (5)「はじめてのPython AIプログラミング」金城俊哉 著 追記 20181005
ver. 0.12 (6)「 scikit-learnとTensorFlowによる実践機械学習」Aurélien Géron追記 20181006 朝
ver. 0.13 (7) 「詳解　ディープラーニング　TensorFlow・Kerasによる時系列データ処理」巣籠悠輔　著 追記 20181006 昼
ver. 0.14 (8)「実践機械学習システム」Willi Richest, Luis Pedro Coelho　著, dockerを使う利点追記。20181006 夕
ver. 0.15 (9)「pythonではじめる機械学習」Andreas C. Muller, Sarah Guido 著、pyside導入, matplotlib再導入例追記。20181007
ver. 0.16 portのエラー, stack overflow URL 追記 20181007 夕
ver. 0.17 pyqt追記 20181008 朝
ver. 0.18  表題変更 20181008 昼
ver. 0.19 (10) with anaconda(10)「実践 Deep Learning ――PythonとTensorFlowで学ぶ次世代の機械学習アルゴリズム」Nikhil Buduma 著追記、20181008 夕
ver. 0.20 (51) with R (1)「入門 機械学習」Drew Conway, John Myles White 著　追記 20181009 早朝
ver. 0.21 (11)「［第2版］Python機械学習プログラミング 達人データサイエンティストによる理論と実践」Sebastian Raschka, Vahid Mirjalili 著　追記 20181009 朝
ver. 0.22 「いくつかの記事は、途中でエラーを解決できずに止まっています。コメント等でご教示くださると幸いです。」追記 20181009 午前
ver. 0.23 (12)「Deep Learning 深層学習」Ian Goodfellow, Yoshua Bengio, Aaron Courville 著 追記 20181009 夕
ver. 0.24 見出し(100) 追記、環境構築(1), (2), (3)追記 20181009 夜
ver. 0.25 項目数 14 (71) 環境構築(1) docker どっかーら、どーやってもエラーばっかり。お詫び(apology) 追記 20181010
ver. 0.26 項目数 15 (72) 環境構築(2)Docker for Windows 追記 20181011
ver. 0.27 項目数 16 (73) 環境構築(3)docker/linux/macos bash スクリプト, ms-dos batchファイル 追記 20181012
ver. 0.28 項目数 17 dockerで機械学習(52) with R (2)「データサイエンスのための統計学入門 ―予測、分類、統計モデリング、統計的機械学習とRプログラミング」Peter Bruce、Andrew Bruce　著　追記 20181013
ver. 0.29 項目数 18 (74) 環境構築(4) R 難関いくつ？　追記 20181014 早朝
ver. 0.30 項目数19 (13) with anaconda(13)カラー図解　Raspberry pi ではじめる機械学習　基礎からディープラーニングまで 20181014 朝
ver. 0.31 項目数 20 (53) with R (3)「RとKerasによるディープラーニング」François Chollet、J. J. Allaire　著 20181014 昼
ver. 0.32 項目数 21 (14) with anaconda(14)「Feature Engineering for Machine Learning」Alice Zheng 著 20181014 午後
ver. 0.33 項目数 22 (15) with anaconda(15)「Deep Learning Cookbook Practical Recipes to Get Started Quickly」Douwe Osinga 著追記 20181014 夕
ver. 0.34 項目数 23 (16) with anaconda(16)「Deep Learning Essentials」 Wei Di, Anurag Bhardwaj, Jianing Wei 著 追記 20181014 夜
 ver. 0.35 項目数24, (75)環境構築(5)docker関連ファイルの管理。C++, JAVA予定, 20181015
ver. 0.36 項目数25, (17)「#Python と #Keras によるディープラーニング」 Francois Chollet著 20181018
ver. 0.37 項目数26, (18)「Deep Learning with Keras」 Antonio Gulli, Sujit Pal著, 候補文献100 20181019 昼
ver. 0.38 項目数27, (19)「Deep Learning Quick Reference」 Mike Bernico著, 20181019 午後
ver. 0.39 項目数28, (20)「Data Science in the Cloud with Microsoft Azure Machine Learning and R」Stephen Elston 著, 20181019 夕
ver. 0.40 項目数29, (21)「Applied Text Analysis with Python」 By Benjamin Bengfort, Tony Ojeda, Rebecca Bilbro, 20181019夜
ver. 0.41 項目数30, (22)「Deep Learning for Computer Vision」 By Rajalingappaa Shanmugamani 20181020 午前
ver. 0.42 項目数31, (23)「Deep Learning with PyTorch」By Vishnu Subramanian 20181020 昼
ver. 0.43 項目数32, (91) with scala(1)「Scala Machine Learning Projects 」By Md. Karim, 20181020 午後
ver. 0.44 項目数33, (24) Machine Learning with Python Cookbook
By Chris Albon, 20181020 夕
ver. 0.45 項目数34, (25)「Mastering TensorFlow 1.x」By Armando Fandango 20181021 午後
ver. 0.46 項目数35, (26)「Natural Language Processing with PyTorch」By Delip Rao 20181021 夕
ver. 0.47 項目数36, (27)「Practical Convolutional Neural Networks」By Md. Karim, Mohit Sewak, Pradeep Pujari 20181021 夜
ver. 0.48 項目数37, (54) with R (4)「Introduction to Machine Learning with R」By Scott Burger 20181022 早朝
ver. 0.49 項目数38, (92) with swift(1)「Machine Learning with Swift」By Alexander Sosnovshchenko 20181022 朝
ver. 0.50 項目数39, (28)「Feature Engineering for Machine Learning」 By Alice Zheng, Amanda Casari 20181022 午前
ver. 0.51 項目数40, (29)「Python Deep Learning」 By Valentino Zocca, Gianmario Spacagna, Daniel Slater, Peter Roelants 20181022 昼
ver. 0.52 項目数41 (30)「Advanced Deep Learning with Keras」 By Philippe Remy 20181022 午後
ver. 0.53 項目数42 (93) with Hadoop(1)「Deep Learning with Hadoop」By Dipayan Dev 20181022 夕
ver. 0.54 項目数43 (55) with R(5)「R Deep Learning Cookbook」 By Philippe Remy 20181022 夜
ver. 0.55 項目数 44 (31)「Fundamentals of Deep Learning」 By Nikhil Buduma 20181023 朝
ver. 0.56 項目数 45 (32)「Hands-On Deep Learning with TensorFlow 」By Dan Van Boxel 20181023 午後
ver. 0.57 項目数 46 (33)「Deep Learning with Theano 」By Christopher Bourez 20181023 夕
ver. 0.58 項目数 47 (34)「Python Deep Learning Cookbook」 By Indra Bakker  20181023 夜
ver. 0.59 項目数 48 (35)「scikit-learn Cookbook」 2nd Edition By Trent Hauck, Julian Avila 20181023 真夜中
ver. 0.60 項目数49 (36)「Learning TensorFlow」 By Itay Lieder, Yehezkel Resheff, Tom Hope 20181024 午前
ver. 0.61 項目数50 (37)「Natural Language Processing with Python Cookbook」 By Pratap Dangeti, Krishna Bhavsar, Naresh Kumar 20181024 昼
ver. 0.62 項目数51 (38)「Mastering Machine Learning with scikit-learn」2nd Edition By Gavin Hackeling 20181024　午後
ver. 0.63 項目数52 (39)「Thoughtful Machine Learning with Python」 By Matthew Kirk 20181024 夕
ver. 0.64 項目数53 (94) with scala(3)「Scala for Machine Learning」 2nd Edition By Patrick Nicolas 20181024 夜
ver. 0.65 項目数54 (85) with Go(1)「Machine Learning With Go」 By Daniel Whitenack 20181025
ver. 0.66 項目数55(86) with Spark(1)「Machine Learning with Spark」 By Rajdeep Dua, Manpreet Singh Ghotra, Nick Pentreath 20181026
ver. 0.67 項目数56(76) with R (6)「Mastering Machine Learning with R 」By Cory Lesmeister 20181028 午前
ver. 0.68 項目数57 (87) with JAVA(1)「Machine Learning: End-to-End guide for Java developers」 By Richard Reese, Jennifer Reese, Bostjan Kaluza, Uday Kamath, Krishna Choppella 20181028午後
ver. 0.69 はじめの方の文書に手入れ。 20181029 午後
ver. 0.70 3.4捨てるのが簡単　追記 20190509
ver. 0.71 標題追記 20190622
ver. 0.72 RaspberryPI, anaconda追記 20190623 
ver. 0.73 2019年発行分追記 20191105
ver. 0.74 誤植訂正 20200103
ver. 0.75 補足 20200307
ver. 0.76 補足 20201226
ver. 0.77 補足 20210117
ver. 0.78 「「Rによる機械学習」の勉強履歴（1）」後追い: dockerで機械学習(77) with R (7)追記 20210427
ver. 0.79 標題にRを 20210428
ver. 0.80 ありがとう追記　20230210
### 最後までおよみいただきありがとうございました。
いいね　💚、フォローをお願いします。
####  Thank you very much for reading to the last sentence.
Please press the like icon 💚　and follow me for your happy life.

<a href="https://b.hatena.ne.jp/entry/s/qiita.com/kaizen_nagoya/items/ddd12477544bf5ba85e2" class="hatena-bookmark-button" data-hatena-bookmark-layout="basic-label-counter" data-hatena-bookmark-lang="ja" title="このエントリーをはてなブックマークに追加"><img src="https://b.st-hatena.com/images/v4/public/entry-button/button-only@2x.png" alt="このエントリーをはてなブックマークに追加" width="20" height="20" style="border: none;" /></a><script type="text/javascript" src="https://b.st-hatena.com/js/bookmark_button.js" charset="utf-8" async="async"></script>
https://b.hatena.ne.jp/guide/bbutton
