---
title: 製造業における機械学習
tags: 機械学習 製造業 深層学習 自動制御 AI
author: kaizen_nagoya
---
### The Qiita article cannot be updated due to system issues. Please refer to GitHub for the latest version.
# 目次
はじめに
背景
・塗装業界で機械学習
・量子計算機の新興企業の提携
製造業と機械学習企業の提携
製造業向け機械学習
製造業とIT企業との提携
おわりに
・深層学習読書会
・・docker で機械学習
・特許
・・特許調査と製造業とIT企業の提携に焦点を絞っている理由
・・特許組織別集計
・情報収集
・・WEBから伺える本気度。
・・Webの確認作業
・・備忘録
参考文献(reference)
・参考資料 on Qiita (references on Qiita)
文書履歴(document history)

# はじめに
## 2017, 2018 深層学習読書会と2019「量子アニーリングの基礎」
2017, 2018年と２年にわたり深層学習の読書会を開催し、名古屋地区の製造業の方とIT企業の方が参加されました。

「ゼロから作るDeep Learning ２自然言語処理編」読書会に参加する前に読んで置くとよい資料とプログラム
https://qiita.com/kaizen_nagoya/items/537b1810265bbbc70e73

2019年は、
「量子アニーリングの基礎」を読む
![68747470733a2f2f71696974612d696d6167652d73746f72652e73332e61702d6e6f727468656173742d312e616d617a6f6e6177732e636f6d2f302f35313432332f64386632366435342d303330632d643861612d363035332d3362316663633337653763332e6a706567-6.jpeg](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/51423/9881843e-1731-be4f-25d4-78a2607c86cb.jpeg)

https://qiita.com/kaizen_nagoya/items/29580dc526e142cb64e9
を7月19日から月１回で開催しました。
https://connpass.com/event/138694/
参加申し込みは@kaizen_nagoyaが受け付けていました。

「「量子アニーリングの基礎」読書会は、どの学識レベルを想定されていますか。」への回答
https://qiita.com/kaizen_nagoya/items/6862d3fe5a8990836df4

# 背景
製造業における機械学習の記事を書き始めようと思ったのは、次の6つの視点から

1) DeepLearningの読書会の参加社が、製造業またはIT企業だった。
2) 日本製鐵が DataRobotで成果をあげたのに対抗してDockerで機械学習の資料を作成中。
3) 塗装業界で人工知能の講演をした。
4) 量子計算機の新興企業の提携関係を知った。
5) 案件等で工場のIoT/AI化を担当している。関係者への説明資料が必要になった。（顔の見える読者）
6) 案件等で工場のIoT/AI特許の調査を始めた。

そして、一行でもいいのでプログラミングしようとしてきた。

６５歳からのプログラミング入門。docker(126)転職(16)
https://qiita.com/kaizen_nagoya/items/1561f910c275b22d7c9f

あなたもdocker, 私もdocker。docker(130)
https://qiita.com/kaizen_nagoya/items/8f2746f10f30b575d0a8

データサイエンティストの気づき『勉強だけして仕事に役立てない人。大嫌い』それ自分かもってなった。
https://qiita.com/kaizen_nagoya/items/d85830d58d8dd7f71d07
### 塗装業界で機械学習
2018年11月8日、中部塗装技術研究会、愛知県工業塗装協同組合の行事で、「IoT/AIの現状と課題　技術士（情報工学）・工学博士　小川清」で、製造業における機械学習と、安全色のJIS改定についてQiitaに掲載した資料を示して講演した。
http://www.nmiri.city.nagoya.jp/seminar/pdf/256.pdf
https://www.slideshare.net/kaizenjapan/deep-learningwithgithubanddocker-125238561?next_slideshow=1

プログラマが知っているとよい色使い(安全色)
https://qiita.com/kaizen_nagoya/items/cb7eb3199b0b98904a35

上記行事で紹介のあった事例は下記。

旭サナック、塗装ロボットが熟練工の動きを再現　教示支援システム開発
https://www.nikkan.co.jp/articles/view/00450188?irextokusetu2017web=1110

塗装工場の未来像を示す　AI・IoT積極的導入へ　旭サナック　
https://www.coatingmedia.com/online/c/post-327.html

製造業とIT企業の組み合わせにより機械学習の利用の費用は百倍くらい違い、成果は１万倍くらい違うような気がする。

<img width="400" alt="196505516_4020123721401577_5687086552191931638_n.jpg" src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/51423/4ba6ed01-ce63-0b49-9ad7-7328c72d5352.jpeg">
技術士(金属部門・総合技術監理部門) 小柳 拓央
## 量子計算機の新興企業の提携
以下の資料は、下記 @yoshi_and_akiさんの量子計算機における新興企業の提携関係を拝見して、機械学習においての提携関係と重ねることにより、今後の展開を想定することを目的とする。

量子コンピューターのスタートアップエコシステム
Yoshi-aki Shimada @yoshi_and_aki 2018年12月21日
https://twitter.com/yoshi_and_aki/status/1075950681326903296

![Du6LPsrUYAEaYKR-3.png](https://qiita-image-store.s3.amazonaws.com/0/51423/7f16958f-d9b3-ac72-95fb-140fc9d57d57.png)

# 製造業と機械学習企業の提携
重要な提携では、両者のWebおよび情報網のWebの３箇所で閲覧できる。
３つの記事の温度差を分析し、１年後、３年後の変化を見ると良い。
##日本製鐵
予測精度が50％超向上、機械学習プラットフォームの効果
http://monoist.atmarkit.co.jp/mn/articles/1810/30/news020.html

機械学習を自動化するプラットフォーム　DataRobot　企業に、次の一手をもらたす、世界屈指のデータ予測分析力。
https://www.itis.nssol.nssmc.com/datarobot/

DataRobot『AI Experience 2018 Tokyo』を開催
https://www.datarobot.com/jp/news/press/aiexperience2018/

【私見】
日本製鐵の例は情報開示していない。DataRobotは、数十種類の機械学習等の手法を並列で計算させ、特徴のあるもの、評価関数の高い成果を応用する。
## デンソー
デンソー、ディープラーニングの研究開発でモルフォと提携
https://tech.nikkeibp.co.jp/dm/atcl/news/15/121101533/

デンソー、画像処理技術を研究開発する 株式会社モルフォと協業推進
https://www.denso.com/jp/ja/news/news-releases/2015/20151211-01/

モルフォがデンソーと次世代画像認識システム向け DNNのアルゴリズムを共同開発
https://www.morphoinc.com/news/denso-morpho-cooperate-adas-ai

量子計算機の専門家がデンソーに転職したのは大きい。
https://www.youtube.com/watch?v=1Bi62GDIqr0&t=1s

## ファナック
ファナック、FAやロボットを機械学習で制御する機能群を販売
https://it.impressbm.co.jp/articles/-/15992

機械学習、深層学習を活用したファナックのAI新機能
https://www.fanuc.co.jp/ja/profile/pr/newsrelease/2018/news20180417_1.html

POSTS TAGED FANUC
https://www.preferred-networks.jp/ja/tag/fanuc

## オムロン
オムロンとベンチャー、工場の不良品防止へＡＩ開発
https://www.sankei.com/west/news/181129/wst1811290029-n1.html

"世界最速AI"開発ベンチャー「エイシング社」と提携
https://www.omron.co.jp/press/2018/11/c1129.html

「オムロン社」との提携について
~「高度1~10m」の生産現場で、製品不良が発生しない製 ラインを実現~
https://aising.jp/wp/wp-content/uploads/2018/11/plessreleases-181129.pdf

## オークマ
オークマとNEC、工作機械のAIがドリル加工の状態を自律診断
https://tech.nikkeibp.co.jp/it/atclact/active/17/071100318/102900618/

AI(人工知能)を活用したドリル加工の診断技術「OSP-AI加工診断」を世界に先駆けて開発
https://jpn.nec.com/press/201810/20181029_03.html

AI（人工知能）を活用したドリル加工の診断技術「OSP-AI 加工診断」を世界に先駆けて開発
https://www.okuma.co.jp/news/2018/181030.html

## 住友電工焼結合金
自動車向け焼結部品の微小亀裂、ＡＩで見逃しゼロへ
https://newswitch.jp/p/12605?from=np

IoT を駆使した焼結部品生産ライン
https://sei.co.jp/technology/tr/bn193/pdf/193-14.pdf

## ＪＦＥスチール
ＡＩで作業員の安全管理　ＪＦＥスチールなど、システム開発
https://www.nikkan.co.jp/articles/view/00499201

国内業界初となるAI画像認識による安全行動サポート技術の導入について
http://www.jfe-steel.co.jp/release/2018/12/181211.html

国内業界初となるAI画像認識による安全行動サポート技術の導入について
https://jpn.nec.com/press/201812/20181211_02.html

## 武蔵精密工業
ギア部品の検品をAIで自動化、武蔵精密工業が自社内で試験運用へ
http://monoist.atmarkit.co.jp/mn/articles/1804/09/news028.html

武蔵精密工業、ABEJAと協業しAIを活用した検品自動化を推進
http://www.musashi.co.jp/newsrelease/news/abejaai.html

武蔵精密工業との資本・業務提携に関するお知らせ
https://abejainc.com/ja/news/article/20180629-2103

## 西松建設
ＡＩで切羽作業判定　西松建設などがシステム
https://www.nikkan.co.jp/articles/view/00488023?isReadConfirmed=true

AIで切羽作業を自動判定する『掘削サイクル判定システム』を開発　－AIで山岳トンネル施工の坑内無人化施工を目指す－
https://www.nishimatsu.co.jp/news/news.php?no=Mjky

西松建設の「山岳トンネルAIソリューション」の詳細がリリースされました。
https://www.smedio.co.jp/news/2018/09/SangakuAISolution.html

## 大林組
大林組とマスワークス、AIによる山岳トンネル工事の切羽評価システムを開発
https://news.mynavi.jp/article/20181221-744091/

クラウドを活用した山岳トンネル工事の切羽（掘削面）評価システムの運用を開始
ディープラーニングで高精度な切羽評価を実施し、工事の安全性・経済性の向上をめざします
https://www.obayashi.co.jp/news/detail/news20181218_1.html

MATLAB ではじめる AI
https://jp.mathworks.com/campaigns/offers/ai-with-matlab.html?s_tid=srchtitle

## 東武
ドローンで線路の安全点検　ドコモと東武、日光・鬼怒川線で実証
https://www.nikkan.co.jp/articles/view/00470031

セルラードローンを活用した鉄道インフラ予防点検の実証実験を開始
http://www.tobu.co.jp/file/pdf/0f5fc3eafc73a1e18b62c9008c0385b4/newsletter_180413.pdf?date=20180413133524
セルラードローンを活用した鉄道インフラ予防点検の実証実験を開始
https://www.nttdocomo.co.jp/binary/pdf/corporate/technology/rd/topics/2018/topics_180413_01.pdf#page=1

## エナジー・ソリューションズ
ドローンによるソーラーモジュール検査にAI自動解析ツール実装
https://news.mynavi.jp/article/20180829-685723/

ドローンによるソーラーモジュール検査にAI自動解析ツールを実装
2MWメガソーラーの解析を3分で実施
https://m-sol.co.jp/news/2018/08/29/droneeye_release/

ドローン＆クラウド ソーラーモジュールIR検査サービス DroneEye
http://www.energy-itsol.com/service/droneeye.html

## 東電ＰＧ
ＮＴＴデータと東電ＰＧ、変電設備をＡＩで異常診断
https://www.nikkan.co.jp/articles/view/00499842

画像・映像解析AI、異音検知AIで変電設備の異常診断を開始
～巡視時間を50％以上削減、約1300箇所の変電所へ導入～
http://www.tepco.co.jp/pg/company/press-information/press/2018/1511683_8687.html

東京電力パワーグリッド、NTTデータが導入する AIを活用した変電設備異常診断ソリューションに「AMY INSIGHT」が採用
https://www.automagi.jp/blog/2018/12/17/東京電力パワーグリッド、nttデータが導入する-aiを/

## FUJI
ＦＵＪＩ、多関節ロボにＡＩ搭載　未設定部品も自動認識https://www.nikkan.co.jp/articles/view/00499520

 FUJIと ALBERT、 多関節ロボットのプログラミングフリーを実現する AI を共同開発
https://www.fuji.co.jp/data/uploads/FUJI-ALBERT_20181213_WEB.pdf

ＦＵＪＩとALBERT、多関節ロボットのプログラミングフリーを実現するAIを共同開発
https://www.albert2005.co.jp/topics/archives/201812/13_110054.html

## 東設土木コンサルタント
ひび割れ、ＡＩと一眼レフで自動検知　キヤノンなどが開発
https://www.nikkan.co.jp/articles/view/00482539?isReadConfirmed=true

電気新聞に「ＡＩひび割れ検知」技術が掲載されました
http://www.tousetu.co.jp/topics18.8.20.html

AIによるひび割れ自動検知技術を参考展示
https://cweb.canon.jp/newsrelease/2018-07/pr-infra.html

## 安川電機
安川電機、ロボットによる対象物の多様なつかみ方を実現するAIピッキング機能を開発
https://iotnews.jp/archives/76801
AIソリューション開発の子会社設立ならびに
AIベンチャー企業 クロスコンパス社との戦略的提携について
https://www.yaskawa.co.jp/newsrelease/news/45421

安川電機とAIピッキング機能を開発
https://www.xcompass.com/news/1620/

## 日本電産シンポ
日本電産シンポ、自動搬送ロボでＤｏｏｇと提携
https://www.nikkan.co.jp/articles/view/00428913?gnr_footer=0007972
自動搬送ロボットに関する業務提携について
http://www.nidec-shimpo.co.jp/new/docs/Shimpo_Doog_teikei170518.pdf
自動搬送ロボットに関する業務提携について
http://jp.doog-inc.com/files/2017-05-18-release.pdf

## エンルート
エンルートとモバイルクリエイト、産業用ドローン・AI・情報システム等の共同開発を開始
https://iotnews.jp/archives/46346

大分県の企業と産業用ドローン、AI、情報システム等の共同開発を開始
https://enroute.co.jp/news/news201701201/

産業用ドローンの製造並びにAI・情報通信システム等共同開発について業務提携
https://www.mcinc.jp/news/産業用ドローンの製造並びにai・情報通信システム/

# 製造業向け機械学習

製造業向け機械学習のシステム、サービスを提供している事例を収集。
製造業名を公開していなかったり、製造業のサイトで相手企業名を公開していない場合がある。両者の提携を示すWebがない資料を含む。

## NVIDIA
【GTC Japan 2017】ホンダの自動運転への取り組みを紹介した本田技術研究所 安井裕司氏のセッション
https://car.watch.impress.co.jp/docs/news/1096836.html

HONDA と NVIDIA 車載製品パートナー
https://www.nvidia.com/ja-jp/self-driving-cars/partners/honda/

## rist
車ミラー AIで検品 村上開明堂が試験導入　作業人員 3分の1に
https://www.nikkei.com/article/DGKKZO28983930U8A400C1L61000/

日経新聞に村上開明堂との取り組みが掲載されました
https://www.rist.co.jp/news/日経新聞に村上開明堂との取り組みが掲載されま/

## 東京エレクトロンデバイス
IoTとAIで生産設備を予知保全、東京エレクトロンDなどが共同開発
https://japan.zdnet.com/article/35118761/

生産設備の予知保全を実現するIoT&AIシステム構築ソリューションを開発
3社で連携して提供を開始
https://www.teldevice.co.jp/pro_info/2018/press_180507.php

ＦＡアドオンＩｏＴゲートウェイ
http://www.kanazawa-es.com/business/KES-IoT-Logic.html

生産設備の予知保全を実現するIoT&AIシステム構築ソリューションを開発
3社で連携して提供を開始
http://www.wingarc.com/public/detail.php?id=827

## ディープインサイト
ディープインサイト、カシオと協業しコンパクトカメラのモジュールにAI推論機能を搭載。
https://prtimes.jp/main/html/rd/p/000000009.000021784.html

ディープインサイト、カシオと協業しコンパクトカメラのモジュールにAI推論機能を搭載 組み込みディープラーニングの適用分野を拡大
https://www.deepinsight.co.jp/download/pdf/pressrelease/pressrelease_kaiber_20180703.pdf

## 株式会社 システム計画研究所
製造業向け外観検査ソフトウェア「gLupe」
https://glupe.jp/ja/

## マイクロソフト
「Raspberry Pi」など小型機器へのAI導入で新たな取り組み
https://japan.cnet.com/article/35103715/

AI’s big leap to tiny devices opens world of possibilities
https://blogs.microsoft.com/ai/ais-big-leap-tiny-devices-opens-world-possibilities/

## otuA（オチュア）
モニター移動ロボット「moniii（モニー）」
https://monoist.atmarkit.co.jp/mn/articles/1803/01/news029_3.html

豊田市「製造業とベンチャー企業のマッチング事業」
ロボット分野：モニター移動ロボット「moniii（モニー）」
https://otua.jp/moniii/

## ロビット
小島プレス工業とロビットによる外観検査の例
https://monoist.atmarkit.co.jp/mn/articles/1803/01/news029_2.html

A I 技術を活用した外観検査の自動化プロジェクト
https://robit.co.jp/doc/01.pdf

## ルネサスエレクトロニクス　
e-AI
https://www.renesas.com/jp/ja/solutions/key-technology/e-ai/e-ai-intelligent-manufacturing.html

## NEC
ＮＥＣ、ＪＳＲに目視検査ソリューション納入　時間50％減
https://www.nikkan.co.jp/articles/view/00478146

NEC、JSRに目視検査ソリューション「AI Visual Inspection」を提供
～対象の品質検査時間を約50％削減～
https://jpn.nec.com/press/201806/20180618_02.html

## Sony
Neural Network Libraries
https://nnabla.org/ja/

## google
TensorFlow Lite for mobile developers (Google I/O '18)
https://www.youtube.com/watch?v=ByJnpbDd-zc

## Xilinx
reVISION が高い応答性とリコンフィギャラブルなビジョン システムを可能にする
https://japan.xilinx.com/products/design-tools/embedded-vision-zone.html

## LeapMind 
IoTの次に来る『DoT』 ── LeapMindが描く、人が機能拡張される世界
https://ledge.ai/theai-2nd-leapmind/

LeapMind社との資本業務提携について
http://www.nttdata.com/jp/ja/news/release/2017/102300.html

## イームズラボ 
カナモト、建機自動停止システム開発　ＡＩカメラで安全確認
https://www.nikkan.co.jp/articles/view/00494551?isReadConfirmed=true

## 東社シーテック
平野製作所、食品機械にＡＩ活用　野菜・果物の不良品判別
http://www.itmedia.co.jp/enterprise/articles/1811/29/news065.html

## SOINN
川重、ＡＩでゴミ処理支援　発電プラント効率操業
https://www.nikkan.co.jp/articles/view/00489528?isReadConfirmed=true

## 村田機械
自動倉庫の監視カメラにAI組み込み荷物の状況をリアルタイムに把握、村田機械が実証開始
https://dcross.impress.co.jp/docs/news/000522.html

自動倉庫用カメラシステム『CSU-100』に組込みディープラーニング（ディープインサイト社『KAIBER』）を搭載
https://www.muratec.jp/corp/news/2018/20180507.html

## みのる産業
野菜農家向け除草ロボ、ドコモなど開発　ＡＩ自律走行
https://www.nikkan.co.jp/articles/view/00499166

## 積水ハウス
積水ハウス、陶板外壁検査にＡＩ活用　在庫40％削減
https://www.nikkan.co.jp/articles/view/00476161?isReadConfirmed=true

陶版外壁「ベルバーン」の静岡工場製造ラインに 画像処理とAI技術による品質検査システムを導入https://www.sekisuihouse.co.jp/company/topics/datail/__icsFiles/afieldfile/2018/06/06/20180606_1.pdf

## 富士フィルム
コンクリ割れ自動検出　大林組、カメラ・ＡＩ活用で手法確立
https://www.nikkan.co.jp/articles/view/00468735

AIによる画像解析技術を利用したコンクリートのひび割れ自動検出手法を確立
https://www.obayashi.co.jp/news/detail/news20180405_1.html

AIを活用した画像解析で橋梁などに生じた幅0.1mm以上のひび割れを自動検出し、点検作業時間を半減！
社会インフラ画像診断サービス「ひびみっけ」提供開始
https://www.fujifilm.co.jp/corporate/news/articleffnr_1271.html

## 三井E&Sマシナリー
一眼レフと連携も…インフラの維持管理をAIがお助け
https://newswitch.jp/p/13876

AIを活用したレーダ探査技術を実用化　画像診断日数を1/4に削減
https://www.mes.co.jp/press/2018/0717_001079.html

外観検査アプリケーション
https://adacotech.co.jp/products/adainspector

## カナモト
カナモト、建機自動停止システム開発　ＡＩカメラで安全確認
https://www.nikkan.co.jp/articles/view/00494551?isReadConfirmed=true

死角を視界に変える接触防止システム ナクシデント
https://www.kanamoto.co.jp/business/b_rental/product/pdf/Naccident.pdf

# 製造業とIT企業との提携
## 森精機
森精機がBUGを完全子会社化
http://seizougenba.com/node/2691

株式会社ビー・ユー・ジーとの資本・業務提携について
https://www.dmgmori.co.jp/corporate/news/pdf/2008_1027_bug.pdf

BUG
https://www.bug.co.jp/product/cntl/index.html

## ソフトバンク
ソフトバンクとトヨタが戦略的提携、ITが全ての「モノ」を支配する時代が到来か!?
https://mynavi-agent.jp/it/geekroid/2018/11/post-57.html

新しいモビリティー社会の実現へ。ソフトバンクとトヨタ自動車の共同記者会見 速報レポート
https://www.softbank.jp/sbnews/entry/20181004_01

## アイシン精機
アイシン精機がヴィッツに出資、車載ソフトウェアの複雑化やISO26262に対応
http://monoist.atmarkit.co.jp/mn/articles/1409/01/news099.html

アイシン精機がヴィッツの第三者割当増資を引き受け
http://www.aisin.co.jp/news/2014/010150.html

アイシン精機がヴィッツの第三者割当増資を引き受け
http://www.witz-inc.co.jp/pdf/press-20140829.pdf

## 横河電機
横河電機、新会社「アムニモ」が発足－IIoTアーキテクチャを活用したサービス提供 
https://www.nikkei.com/article/DGXLRSP480039_X10C18A5000000/

IIoTアーキテクチャ開発に向けIT分野の先進企業4社と協業
IIoTを活用しお客様の経営効率向上に貢献
https://www.yokogawa.co.jp/cp/press/2017/pr-press-2017-0201-ja.htm

## 富士ゼロックス
オプティムと富士ゼロックス、モバイル端末管理分野で業務提携 
「モバイルあんしんマネジメントサービス」に「Optimal Biz」エンジンを搭載
https://www.optim.co.jp/news-detail/14015

富士ゼロックスとの資本提携関係を強化
https://www.optim.co.jp/news-detail/17959

IT環境運用支援サービス群(ITあんしんサービ スパックII 、IT監視運用支援サービス)
https://site-search.fujixerox.co.jp/click?url=https%3A%2F%2Fwww.fujixerox.co.jp%2Fcompany%2Ftechnical%2Ftr%2F2013%2Fpdf%2Fp_01.pdf&query=オプティム&charset=UTF-8&site=PDSKNZZA&group=1
## リコー
リコー、AIによるWeb解析サービス提供のWACULと業務提携
https://news.mynavi.jp/article/20181213-740295/

リコー、AIによるWeb解析サービスを提供するWACUL社との業務提携および出資
https://jp.ricoh.com/release/2018/1212_1.html

総額5.6億円のファイナンスの実施および株式会社リコーとの協業契約締結のお知らせ
https://wacul.co.jp/pressrelease/finance_and_partnership/?fbclid=IwAR37MYcsZwwlFv9uZXaYM_rqCWfFHsDimjvLp84yr7FgZeyF8NCl_D3otU4

## キャノン
キヤノンMJとコージェントが協業、高精度な「手書きOCR」提供
http://ascii.jp/elem/000/001/574/1574167/

スタートアップ企業と協業し「手書き AI OCRソリューション」を提供開始
～企業の業務プロセスを変革し働き方改革を支援～
https://cweb.canon.jp/newsrelease/2017-10/pr-tegaki-ai-ocr.html

スタートアップと協業し「手書き AI OCRソリューション」を提供開始
https://www.cogent.co.jp/news/2017-10-25-canon-tegaki-solution/

## 富士通
富士通とHERE、先進モビリティサービスと自動運転で提携
https://response.jp/article/2017/11/07/302175.html

富士通とHERE、先進モビリティサービスと将来の自動運転で提携
http://pr.fujitsu.com/jp/news/2017/11/7-1.html

## 日立製作所
日立、中国テンセントとIoTで提携 
https://www.nikkei.com/article/DGXMZO35159220Q8A910C1EAF000/

日立とテンセントが、IoT 分野における戦略的提携に合意
http://www.hitachi.co.jp/New/cnews/month/2018/09/0910b.pdf

## Yahoo
J.Scoreとヤフーが業務提携、データを活用した金融サービス
https://news.mynavi.jp/article/20171222-561203/

J.ScoreとYahoo! JAPANの業務提携契約の締結に関するお知らせ
https://www.jscore.co.jp/company/news/2017/1222_01/

J.ScoreとYahoo! JAPANの業務提携契約の締結に関するお知らせ
https://about.yahoo.co.jp/pr/release/2017/12/22a/

## パナソニック
パナソニック、AIスマートハウスの"CASPAR"と提携
https://news.mynavi.jp/article/20180912-692312/

AIを活用したスマートホーム開発加速に向け「BrainofT社」と連携
https://news.panasonic.com/jp/press/data/2018/09/jn180912-3/jn180912-3.html

Panasonic Entered Partnership with Caspar
to Develop Artificial Intelligence Smart Home System
https://caspar.ai/press/

## ALBERT
ALBERT、人工知能関連事業強化を目的に電気通信大学と共同研究を開始
https://iotnews.jp/archives/12211

ALBERT、人工知能関連事業強化を目的に電気通信大学と共同研究を開始
https://www.albert2005.co.jp/release/archives/201602/03_110019.html

”ALBERTと電通大 教育用途のAI開発 出題、人に合わせて”
https://www.uec.ac.jp/news/media/2015/

## 三菱電機
オラクルと三菱電機、製造業向けIoT基盤で連携
https://businessnetwork.jp/Detail/tabid/65/artid/5564/Default.aspx

【記録】オラクルは、2017年以前のニュースはリンク切れ。三菱電機はオラクルとの連携記事見当たらず。

# おわりに
## docker で機械学習
なぜdockerで機械学習するか 書籍・ソース一覧作成中 (目標100)
https://qiita.com/kaizen_nagoya/items/ddd12477544bf5ba85e2

dockerで機械学習 with anaconda(1)「ゼロから作るDeep Learning - Pythonで学ぶディープラーニングの理論と実装」斎藤 康毅 著
https://qiita.com/kaizen_nagoya/items/a7e94ef6dca128d035ab

dockerで機械学習with anaconda(2)「ゼロから作るDeep Learning2自然言語処理編」斎藤 康毅 著
https://qiita.com/kaizen_nagoya/items/3b80dfc76933cea522c6

## 特許
情報収集の対象企業の網羅性を確保するためgoogle特許検索した。

google特許検索
https://patents.google.com/
で検索した。出願人の分布を示す。 20190113現在

詳細な内容は別記事
深層学習・機械学習　出願特許
https://qiita.com/kaizen_nagoya/items/38085a4fb38cd1d9e4d8

### 特許集計

|  | machine learning | deep learning | m/d |
|:--|--:|--:|--:|
| machine learning | 141104 |  |  |
| deep learning |  | 20220 | 6.97 |
| factory automation | 178 | 43 | 4.13 |
| factory | 4058 | 570 | 7.11 |
| machine tool | 401 | 92 | 4.35 |
| automatic control | 1331 | 254 | 5.24 |
| motor | 12325 | 1864 | 6.61 |
| real time | 54279 | 6792 | 7.99 |
|||||
| image processing | 20889 | 5285|3.95|
m/d(小数点以下３桁切り捨て)

machine learningの件数をdeep learningの件数で割った結果は、
deep learningで特許件数が増えてきた分野かどうかの推測の指標として想定した。
m/dの値が小さい方が、近年増加したと推定する。
この推測を確認するため、image processingの件数を示す。
image processingは、deep learningの代表例で、人間の認識を機械学習が超えた一分野である。
image processing のm/dの値3.95から　machine learning/ deep learningの値6.97までがdeep learningが増加している領域と想定する。6.97以上があまり増加していないかもしれない領域と仮定する。3.95より小さい値の領域は未調査。

### 特許調査と製造業とIT企業の提携に焦点を絞っている理由
AI/IoT関連の仕事をしていく上で、特許は避けられない障壁である。
回避する方法で思いつくのは、次の５つ

１　一番特許を持っている組織と提携する
２　一番特許を持っている組織は、提携の金額が高い場合に、二番目、三番目と提携する
３　既存の特許を回避する方法を探す。
４　既存の特許にない方法は、自社で特許を申請する
５　規格とOpen Sourceを頼りに、特許調査に費用を配分しない

ここでは、特許は、AI/IoTに関するものと、製造物に関するものの両方である。

製造業とIT企業の提携は、二つの部門の特許問題を、ひょっとしたら一気に解決できるかもしれないという可能性がある。量子計算機も同様。

### 特許組織別集計
| "machine learning" and motor |  12325件  |
|:--|:--|
| Fanuc Corporation | 5.20% |
| Brain Corporation | 4% |
| Searete Llc  A Limited Liability Corporation Of The State Of Delaware | 3.60% |
| Edsa Micro Corporation | 3.10% |
| Rockwell Automation Technologies  Inc. | 2.60% |
| ファナック株式会社 | 2.40% |
| Qualcomm Incorporated | 1.80% |
| 江苏大学 | 1.60% |
| Gm Global Technology Operations  Inc. | 1.60% |
| Fitbit  Inc. | 1.40% |
| Google Inc. | 1.10% |
| Honda Motor Co.  Ltd. | 1.10% |
| Bodymedia Inc. | 0.90% |
| Robert Bosch Gmbh | 0.80% |
| Toyota Motor Engineering & Manufacturing North America | 0.80% |
| Power Analytics Corporation | 0.80% |
| Toyota Jidosha Kabushiki Kaisha | 0.80% |
| The Regents Of The University Of California | 0.80% |
| Koninklijke Philips Electronics N.V. | 0.80% |


| "deep learning" and "motor" | 1864件 |
|:--|:--|
| 엘지전자 주식회사 | 6.40% |
| ファナック株式会社 | 4.60% |
| Samsung Electronics Co.  Ltd. | 3.70% |
| Facense Ltd. | 3.60% |
| Fanuc Ltd | 2.60% |
| 삼성전자주식회사 | 2.60% |
| 주식회사 만도 | 2.10% |
| General Electric Company | 1.90% |
| 開 顔 | 1.90% |
| Fanuc Corporation | 1.60% |
| 軍 呉 | 1.60% |
| 현대자동차주식회사 | 1.60% |
| Honda Motor Co. Ltd. | 1.30% |
| オムロン株式会社 | 1.10% |
| 株式会社エンルート | 0.90% |
| 银江股份有限公司 | 0.90% |
| Intel Corporation | 0.90% |
| uBiome Inc. | 0.90% |
| 삼성전자 주식회사 | 0.90% |

日本企業では、
ファナック
オムロン
三菱電機
東京エレクトロン
横河電機
株式会社リコー
株式会社安川電機
キャノン
Yahoo
株式会社Ｗｇｒ
セイコーエプソン株式会社 
日本電産株式会社 
オークマ
ソニー
NEC
国立大学法人電気通信大学
株式会社日立製作所
ホンダ
トヨタ
Fuji Xerox
富士通
パナソニック
株式会社エンルート

海外では、
Microsoft 
IBM
Google
Intel 
Nvidia
Qualcomm
Samsung
GE
など。

下記資料で網羅していない組織を順次調査中。
## 情報収集
情報は名古屋地区に偏りが大きい。名古屋地区の事例は、仕事柄目に付きやすいから。
職務上の機密には基づいていない。

製造業における機械学習の成果、提携関係を調べ、対外的に公開している事項を整理する。
製造業では、ソフトウェアの開発を担当している企業名を公開していない場合がある。
製造業における機械学習の進展および、製造業で利用可能な機械学習のシステム、サービスが網羅的に確認しづらいことがある。

### WEBから伺える本気度。
1. 両者および情報媒体が、３様に技術、視点を提供している。
2. 両者が同一の広報資料のみを掲示し、情報媒体が報道している。
3. 一方および情報媒体が報道している。
4. 報道媒体だけが報道している。
5. 一方だけが報道している。

隠している場合が本気のこともある。

### Webの確認作業
企業名で企業Webを検索。企業Webで提携企業名で検索。

1. 商品・サービスのWebと企業Webとが別のところがある。
2. 企業Webに、検索機能がないところがある。
3. 企業Webで、取引先名を明示しないところがある。
　提携企業名では検索できず、商品名、サービス名、AI、ディープラーニング等で検索。
4. 企業Webで、報道資料を掲載していないところがある。
5. 企業Webで、報道資料しか掲載していないところがある。
　　関連資料が企業Web内にない。
6. 研究開発は親会社・関連会社で情報を公開しているところがある。
　　両者の研究は一方のWebにしかない。
7. 該当する研究、商品、サービスの市場向けの情報だけで、特定企業との研究は開示していない場合がある。
### 備忘録
機械学習、深層学習、統計的手法、量子計算機による解法などを並列で計算させ、そのうち有効な手法を発見することを検討。dockerで機械学習を実施している背景。

機械学習による統計・確率的な手法とともに、数理的手法による厳密な解、ソフトウェアの検証なども行なっている。
JAXA/IPA クリティカルソフトウェアワークショップ WOCS言語関連発表(改定版)
https://qiita.com/kaizen_nagoya/items/3447b1bc4ee6014e6739

https://researchmap.jp/josvhrsga-49935/?lang=english

# 参考文献(reference)
2018年 AI / 機械学習 NEWS 総まとめ【業界MAP付】
https://leapmind.io/blog/2018/12/26/2018-ai-news/

組込み向けDeep Learning フレームワーク コキュートスの紹介 株式会社パソナテック 西日本支社 夏谷 @SWEST
https://swest.toppers.jp/SWEST19/program/pdfs/s2b_proceeding.pdf

 機械学習モデルを搭載した セーフティクリティカルなシステムの 品質保証 桑島洋、安岡宏俊、中江俊博 株式会社デンソー 東京支社 電子基盤先行開発室 @SWEST
https://swest.toppers.jp/SWEST20/program/pdfs/s2b_public.pdf

特許データからビジネスチャンスを探る
人工知能に取り組む全企業 2018
https://www.neotechnology.co.jp/wp/wp-content/uploads/2018/03/d3c27c8c10ce1cb46d88207bdcff49ff.pdf

## 参考資料 on Qiita (references on Qiita)
製造業はオワコンと嘆く前に自身でAI取り入れ方を考えてみる
https://qiita.com/takatsukaband/items/1fc7ea26ac45fd0dead3

製造業はオワコンと嘆く前に自身でAIと品質管理について思いを馳せてみる
https://qiita.くcom/takatsukaband/items/2e7cf278f5ce97cc214c

異常検知関連の本5冊読んだので書評書く。
https://qiita.com/Ringa_hyj/items/84037657b2437ca661ca

SHAP値を用いて機械学習（予測モデル）の予測結果を解釈してみた
https://qiita.com/DS27/items/9059667acc580ca9bbb7

多変量統計的プロセス管理（MSPC）を実装してみた
https://qiita.com/DS27/items/165363158273e441e877

機械学習（回帰モデル）で使用する評価指標を整理してみた
https://qiita.com/DS27/items/2204b10888a19869e083

疎構造学習による異常検知を実装してみた
https://qiita.com/DS27/items/279306656d0b41918846

機械学習（予測モデル）をscikit-learnを用いて様々な手法を実装してみた
https://qiita.com/DS27/items/aa3f6d0f03a8053e5810

(機械学習)大量の特徴量を削減する上で有用な手法である主成分分析を学んだ＋製造業（特に機械設備保全）への展開を考えた
https://qiita.com/Fumio-eisan/items/1a4a8d19b235f17bd610

Python+MX Component で生産設備(三菱 Q-PLC )を制御するまで
https://qiita.com/SO326/items/a1483018c41023897e91

### 自己参照(self reference)

自動制御、制御工学一覧（０）
https://qiita.com/kaizen_nagoya/items/7767a4e19a6ae1479e6b

一覧の一覧( The directory of directories of mine.) Qiita(100)
https://qiita.com/kaizen_nagoya/items/7eb0e006543886138f39

量子コンピュータプログラムへの道
https://qiita.com/kaizen_nagoya/items/37c90488c87bbe9f2d71

量子計算機　特許
https://qiita.com/kaizen_nagoya/items/4429b2f5ed1a49180b55

物理記事　上位100
https://qiita.com/kaizen_nagoya/items/66e90fe31fbe3facc6ff

数学関連記事１００
https://qiita.com/kaizen_nagoya/items/d8dadb49a6397e854c6d

言語・文学記事　１００
https://qiita.com/kaizen_nagoya/items/42d58d5ef7fb53c407d6

医工連携関連記事一覧
https://qiita.com/kaizen_nagoya/items/6ab51c12ba51bc260a82

通信記事１００
https://qiita.com/kaizen_nagoya/items/1d67de5e1cd207b05ef7

自動車　記事　１００
https://qiita.com/kaizen_nagoya/items/f7f0b9ab36569ad409c5

# OSEK 参考資料(Reference)
WSL上にnxtOSEKの開発環境を構築する方法
https://qiita.com/TsuneoNakanishi/items/76999b2e6b4e9cd30117

Raspberry Pi 3 Model B+ 向けにリアルタイムOSを実装してみた話
https://qiita.com/tenkoh2/items/baa8e0b6c09669793b4f

[メモ] TrampolineRTOSでLチカ (OSEK/VDX & AUTOSAR APIにあわせたRTOS)
https://qiita.com/mt08/items/65f2ac9bbdae09a34470

MacでLego Mindstorms NXT環境構築 in 2018
https://qiita.com/vivid344/items/2f23f846cd3b135c5a74

ETロボコン開発環境構築 for Mac
https://qiita.com/tac0x2a/items/b1d82050c660935765ef

[メモ] ERIKA様でLチカ (Arduino)
https://qiita.com/mt08/items/adc90efbbfc938be7cc4

COFEを使って水-エタノールの分離シミュレーションを行う
https://qiita.com/kijuky/items/0979327cf7e7c091da02

## OSEK 自己参考(Self Reference)
OSEKはもう流行らないのでしょうか。AUTOSAR（64）OSEK(1) https://qiita.com/kaizen_nagoya/items/b87687254b11f30cc2ee
OSEKを図から理解 OSEK(2) https://qiita.com/kaizen_nagoya/items/f87a7ff5aeb63803a022
OSEK OS（AUTOSAR OS）をざっくり理解するには OSEK(3) https://qiita.com/kaizen_nagoya/items/c68c0b86b97d4a90e6e2
calloutとcallback, OSEK/VDX OS and AUTOSAR OSEK(4) https://qiita.com/kaizen_nagoya/items/b95b81354d07b9172a56
OSEK/VDX ISO and 2.23 OSEK(5) https://qiita.com/kaizen_nagoya/items/4d6bcec01e0132f9c41c
OSEK/VDX OSEK(6) https://qiita.com/kaizen_nagoya/items/a7720994f2178a15be81
ISO OSEK/VDX and ISO Linux OS 同梱ソースをC++またはRUSTで書く企画　OSEK(7) https://qiita.com/kaizen_nagoya/items/27899e936c90b415d700
OSEK 記事で views 100,000を目指して　OSEK(8) https://qiita.com/kaizen_nagoya/items/ff45ee55566eeff5f62e
自動車用OSを網羅する OSEK(9) https://qiita.com/kaizen_nagoya/items/a61144daf500a3f2b4f4
Smallest Set Profile and Automotive Profile, OSEK(10) https://qiita.com/kaizen_nagoya/items/0c5484f6562cc259e7f0
Exclusive Area, OSEK(11)　https://qiita.com/kaizen_nagoya/items/d87ff4e08378dbcf68a7
自動車のソフトウェア、例えばAUTOSAR の仕事を始めてする方に, OSEK(12) https://qiita.com/kaizen_nagoya/items/1832634788c23498e054
名古屋で自動車関係のソフトウェア設計する際にあるといいかもしれない知識, OSEK(13) https://qiita.com/kaizen_nagoya/items/9f01d55e4bd0bd931c96
single task os and data, OSEK(14) https://qiita.com/kaizen_nagoya/items/6acbd5d2cfd3ed8bca60
ISO Road vehicles - Diagnostics 等規格72(調査中)。百規格、百記事をめざして。 https://qiita.com/kaizen_nagoya/items/51e29d318585a4219985
Automotive Software Expert Examination Exercise, Examples or Extract. OSEK(16) https://qiita.com/kaizen_nagoya/items/1762e0612ef01e036efb
自動運転資料集(1) OSEK(17) https://qiita.com/kaizen_nagoya/items/42eb2129e281f25eaab8
TOPPERS of the YearとAUTOSAR, AUTOSAR(39), OSEK(18) https://qiita.com/kaizen_nagoya/items/f241bb4a819733110b7a
Autosar 2.0を読む, AUTOSAR(25), OSEK(19) https://qiita.com/kaizen_nagoya/items/b44a1047c2c517d522fe
IT関連技術でお世話になった方々, OSEK(20) https://qiita.com/kaizen_nagoya/items/8a5bf487594cd106e8b8
AUTOSARの４つの入力, OSEK(21)  https://qiita.com/kaizen_nagoya/items/72cef6028b9697f7968e
AUTOSAR これだけ知っていればなんとかなる。OSEK(22) https://qiita.com/kaizen_nagoya/items/7a63e706bfb8f331cfe4
電動機故障診断(ACサーボモータを中心に) https://qiita.com/kaizen_nagoya/items/756d19527d5f862e8085
AUTOSARと国際規格。AUTOSAR（65), OSEK(24)  https://qiita.com/kaizen_nagoya/items/4ddba03efb942969b125
AUTOSAR入門, AUTOSAR(16), OSEK(25) https://qiita.com/kaizen_nagoya/items/5e43b8ef0935c32ee11d
MISRA-C 2012 Referenceに掲載している文献の入手可能性を確認 https://qiita.com/kaizen_nagoya/items/96dc8b125e462d5575bb
Autosarの課題, OSEK(27)  https://qiita.com/kaizen_nagoya/items/617d10b0e34143030600
AUTOSAR: The past 20 years and he next 10 years, OSEK(28) https://qiita.com/kaizen_nagoya/items/2dab0707c01059c152c4
Autosar文書を読む（準備), OSEK(29)　https://qiita.com/kaizen_nagoya/items/5f547173544703d267aa
AUTOSARが手に取るように分かるようになる。AUTOSAR(29), OSEK(30) https://qiita.com/kaizen_nagoya/items/ae092ea6aef89cdc15df
posixとethernet, osekとTCP/IP, osek(31) https://qiita.com/kaizen_nagoya/items/73b79a4a56f433bd53c0
斉藤直希「組み込み向けリアルタイムOSの基礎知識を整理する」を整理する, OSEK(32) https://qiita.com/kaizen_nagoya/items/d305e83b37d0c57dceb3
TOPPERS活用アイデア・アプリケーション開発コンテスト受賞作品紹介　まとめ作成中, OSEK(33) https://qiita.com/kaizen_nagoya/items/72b882d96b2841f25faf
はじめてのAUTOSAR(classic platform) ＜エンジニア夏休み企画>【読書感想文】, OSEK(34) https://qiita.com/kaizen_nagoya/items/696ad320f76f284664d7
AUTOSARとSimulink: Adaptive Platform, Classic Platformとマルチコア・共通化, OSEK(35) https://qiita.com/kaizen_nagoya/items/d613b0b14bfd91989a13
AUTOSAR Abstract Platformへの道（詳細編）, OSEK(36) https://qiita.com/kaizen_nagoya/items/cb217133884fa0a2c704
building block：AUTOSAR Abstruct Platform , OSEK(37), https://qiita.com/kaizen_nagoya/items/bf7c17624f648fb9f392
系建築家(system architect)になるには, OSEK(38) https://qiita.com/kaizen_nagoya/items/8c341e69233cb32f6275
自己紹介 OSEK(39) https://qiita.com/kaizen_nagoya/items/90aa368f296613ec93b5
AUTOSAR 「完全に理解した」, OSEK(40) https://qiita.com/kaizen_nagoya/items/51983798ad7902b33cb1
Architecture 「toaster model」を出発点として, OSEK(41)　https://qiita.com/kaizen_nagoya/items/9ab8b4bea3ff4e94b192
AUTOSAR Q&A。 AUTOSAR(30), OSEK(42) https://qiita.com/kaizen_nagoya/items/ba6c02b772e9617dc138
「人生で影響を受けた本100冊」に28冊足す計画（18冊）, OSEK(43) https://qiita.com/kaizen_nagoya/items/3ae6633725df77261df8
Bosch Automotive Handbook and so on. OSEK(44) https://qiita.com/kaizen_nagoya/items/8e330ce57880f04d71d9
自動車　記事　１００, OSEK(45) https://qiita.com/kaizen_nagoya/items/f7f0b9ab36569ad409c5
何故、今、国際規格なのか。OSEK(46) https://qiita.com/kaizen_nagoya/items/6970577e3e94e5b51ccc
名古屋のIoTは名古屋のOSで。仮説（186）OSEK(47) https://qiita.com/kaizen_nagoya/items/fa6694bbec50723ea90a
作業診断(process assessment)を成功させる５つの鍵。失敗する５つの罠 。仮説（50） https://qiita.com/kaizen_nagoya/items/bcdc60db20e8d7081fab
AUTOSAR教材作成３年計画, AUTOSAR(19) OSEK(49) https://qiita.com/kaizen_nagoya/items/84d8f1ecbbe7af7803af
AUTOSARの利点と方向性, OSEK(50) https://qiita.com/kaizen_nagoya/items/681902476520cccf3c3e
TOPPERS のAUTOSARへの貢献(更新中), AUTOSAR(15), OSEK(51) https://qiita.com/kaizen_nagoya/items/d363cf06e2176207b391
TOPPERS の AUTOSAR への貢献 II (改定中), OSEK(52) https://qiita.com/kaizen_nagoya/items/4614c04cfff70a241f77
A big wrapping cloth with the miniature garden, OSEK53) https://qiita.com/kaizen_nagoya/items/96411f20632e7f3ff73a
AUTOSAR R23-11 資料整理の計画（年越し懇親会遠隔開催時間投票含む）OSEK(54)　https://qiita.com/kaizen_nagoya/items/6b939e2373e0e6047ae8
自動車用（車載）ソフトウェアの基本設計提案を作る。OSEK(55)  https://qiita.com/kaizen_nagoya/items/9c218e65d98084b24dfe
自動車用（車載）ソフトウェアの基本設計提案を作る(2), OSEK(56) https://qiita.com/kaizen_nagoya/items/38cb4710410a0d51e7a0
マルチコアの壁, OSEK(67) https://qiita.com/kaizen_nagoya/items/f38e47574905c80c0706
実時間処理, OESK(58) https://qiita.com/kaizen_nagoya/items/1e36077736d11960bb64
CPU マルチコア　マルチOS, OSEK(59) https://qiita.com/kaizen_nagoya/items/6bdb6116f0aa50c5372a
AUTOSAR related Standard, OSEK(60) https://qiita.com/kaizen_nagoya/items/13b163f8515615ecc648
「あなたがAUTOSARのEditorだったらどの文書をどう書き換えたいか」選手権(0), OSEK(61) https://qiita.com/kaizen_nagoya/items/0055bb88f43f98a61739
Call back, OSEK(62) https://qiita.com/kaizen_nagoya/items/8c76f5e05cbd9125f86d
C言語教育はCコンパイラの写経で, OSEK(63) https://qiita.com/kaizen_nagoya/items/088a9906797559cd8b8a
Reentrant とRecursive, OESK(64)　https://qiita.com/kaizen_nagoya/items/cdc028f73fe2dea3090f
AUTOSARの基礎の仮説, OSEK(65) https://qiita.com/kaizen_nagoya/items/ceaf360e69f81c332677
Linuxを学ばずに使う, OSK(56)　https://qiita.com/kaizen_nagoya/items/b9859782bab0cf6c78a4
AUTOSAR わかりにくいこと12, AUTOSAR(27), OSEK(67) https://qiita.com/kaizen_nagoya/items/68b0da5bee1421200a11
お盆には「箱庭」記事を書きましょう「もくもく会」の題材になる（１）, OSEK(68) https://qiita.com/kaizen_nagoya/items/a22bf2b1dab0ad3258d4
逆も真：社会人が最初に確かめるとよいこと。OSEK(69) https://qiita.com/kaizen_nagoya/items/39afe4a728a31b903ddc
プログラマが安全工学シンポジウムで発表する動機、題材、技法。安全（22）OSEK(70) https://qiita.com/kaizen_nagoya/items/b7adf3001eb325166e52
プログラマにも読んでほしい「QC検定にも役立つ！QCべからず集」OSEK(81)　https://qiita.com/kaizen_nagoya/items/d8ada7b7fceafe2e5f0e
AUTOSAR文書の読み方（文書番号と発行年）, AUTOSAR(23), OSEK(72) https://qiita.com/kaizen_nagoya/items/daa3f7de7e86b89bcc33
計算機系事故記録(computer system trouble record), OSEK(73) https://qiita.com/kaizen_nagoya/items/910847f01379903e40c8
basic: プログラムジェネレータジェネレータ。構造屋(architect)としての成功事例3失敗事例６, OESK(74) https://qiita.com/kaizen_nagoya/items/117c7a1b6dad97470ae9
AUTOSAR記事一覧, OSEK(75) https://qiita.com/kaizen_nagoya/items/89c07961b59a8754c869
AUTOSAR 文書番号, OSEK(76) https://qiita.com/kaizen_nagoya/items/8b894228a0b76c2265c7
参考文献の参考文献は参考文献だ。清水吉男「「派生開発」を成功させるプロセス改善の技術と極意」を超えて, OSEK(77) https://qiita.com/kaizen_nagoya/items/562a0cf784cf92bc0ebb
ボッシュ自動車handbook(英語)11版(0-1) 課題と記事一覧new, OSEK(78) https://qiita.com/kaizen_nagoya/items/a9d2887bf2a7598dc8e5
プログラマの「プログラムが書ける」思い込みは強みだ。３つの理由。仮説（168）統計と確率(17) , OSEK(79) https://qiita.com/kaizen_nagoya/items/bc5dd86e414de402ec29
最新規格のコンパイル, OSEK(80) https://qiita.com/kaizen_nagoya/items/4e23544a7ee8a8f19b68
模型駆動開発(Model Driven Design)への道、OSEK(81)　https://qiita.com/kaizen_nagoya/items/bb4d73bfb3cbba88727f
MATLAB 完全に理解するには, OSEK（82) https://qiita.com/kaizen_nagoya/items/867e8743fa813be9b37c
製造業における機械学習, OSEK(83) https://qiita.com/kaizen_nagoya/items/fbe846de16f74bea1d6f
自動車技術会 2020年春季大会 Summarized Paper 単語帳 OSEK(84)https://qiita.com/kaizen_nagoya/items/758922c754be557571a4
NASAを超えるつもりがあれば読んでください。OSEK(85) https://qiita.com/kaizen_nagoya/items/e81669f9cb53109157f6
プロセスは未定義と定義するのがよい。仮説(67), OESK(86) https://qiita.com/kaizen_nagoya/items/0f3a1174f81935bb6d85
交通事故死を減らすのにプログラマが主導できる事項13選。仮説（21）。安全(26), OSEK(87) https://qiita.com/kaizen_nagoya/items/4d46bbf0dde44d7bb99a
AUTOSARはどこから来て、どこへ行くか。, AUTOSAR(13), OSEK(88) https://qiita.com/kaizen_nagoya/items/b605326a1aebe79b5d85
安全工学シンポジウムに向けて。安全（0）OSEK(89)　https://qiita.com/kaizen_nagoya/items/c5d78f3def8195cb2409
オープンソース計算機模擬試験による安全関連系の設計と分析。安全（23）, AUTOSAR(37)、OSEK(90) https://qiita.com/kaizen_nagoya/items/a317bf6570cb3bdf185b
プログラマが安全な系のためにできること。仮説(66), OSEK(91) https://qiita.com/kaizen_nagoya/items/a9667ab0d1e48438edba
AUTOSAR文書、参考文献、短縮名(short name:略号)一覧作成自動化の可能性, OSEK(92) https://qiita.com/kaizen_nagoya/items/005c4d82d8c1af7ce103
Autosar文書を読む(感想), OSEK(93) https://qiita.com/kaizen_nagoya/items/b517392610cdf85514f5
JAXA/IPA クリティカルソフトウェアワークショップ WOCS言語関連発表(改定版), OSEK(94) https://qiita.com/kaizen_nagoya/items/4789832baf494cb74626
電動機制御算譜（プログラム）設計における３つの罠６つの教訓（実機）, OSEK(95) https://qiita.com/kaizen_nagoya/items/b39b6b7ba0d90dff471d
参考文献駆動執筆(references driven writing)・デンソークリエイト編, OSEK(96) https://qiita.com/kaizen_nagoya/items/b27b3f58b8bf265a5cd1
プログラマによるプログラマのプログラマの子供のための自動車安全絵本企画。安全(31), OSEK(97) https://qiita.com/kaizen_nagoya/items/0ab47d8fca2933f8877a
安全分析においてHAZOPで想定外を洗い出すために, OESK(98) https://qiita.com/kaizen_nagoya/items/11f1ace6f4c150248903
## 一覧
物理記事　上位100
https://qiita.com/kaizen_nagoya/items/66e90fe31fbe3facc6ff

量子(0) 計算機, 量子力学
https://qiita.com/kaizen_nagoya/items/1cd954cb0eed92879fd4

数学関連記事１００
https://qiita.com/kaizen_nagoya/items/d8dadb49a6397e854c6d

統計(0)一覧
https://qiita.com/kaizen_nagoya/items/80d3b221807e53e88aba

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

仮説（0）一覧
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

線網（Wi-Fi）空中線(antenna)(0) 記事一覧
https://qiita.com/kaizen_nagoya/items/5e5464ac2b24bd4cd001

OSEK OS設計の基礎　OSEK(100)
https://qiita.com/kaizen_nagoya/items/7528a22a14242d2d58a3

Error一覧 error(0)
https://qiita.com/kaizen_nagoya/items/48b6cbc8d68eae2c42b8

プログラマによる、プログラマのための、統計(0)と確率のプログラミングとその後
https://qiita.com/kaizen_nagoya/items/6e9897eb641268766909

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

＜この記事は個人の過去の経験に基づく個人の感想です。現在所属する組織、業務とは関係がありません。＞
This article is an individual impression based on the individual's experience. It has nothing to do with the organization or business to which I currently belong.
### 文書履歴(document history)
ver. 0.01 初稿 20190109 午前
ver. 0.02 デンソー、NVIDIA、ソフトバンク追記 20190109 午後
ver. 0.03 アイシン精機, ＪＦＥスチール, 西松建設追記 20190109 夜
ver. 0.04 東武、大林組、イームズラボ、本気度、参考資料追記 20190110 午前
ver. 0.05 東電PG、エナジー・ソリューションズ、FUJI　追記 20190110 午後
ver. 0.06 塗装事例：旭サナック、数理的手法　追記 20190110 夜
ver. 0.07 参考文献、備忘録　追記 20190111 朝
ver. 0.08 富士フィルム, カナモト,三井E&Sマシナリー 追記 20190111 昼
ver. 0.09 Webの確認作業追記 20190111 夜
ver. 0.10 表現をよりわかりやすく加筆、はてなブックマーク追加 20190112 朝
ver. 0.11 背景等追記 20190112 夕
ver. 0.12 目次追加 20190113 昼
ver. 0.13 特許項目追加 20190113 夕
ver. 0.14 項目順番入れ替え 20190113 夜
ver. 0.15 特許検索による網羅性の確認 20190114 夕
ver. 0.16 横河電機、三菱電機、東京エレクトロンデバイス　追記 20190114 夜
ver. 0.17 安川電機、リコー、キャノン　追記 20190115 朝
ver. 0.18 日本電産シンポ, 日立製作所, 富士通　追記　20190115 午後
ver. 0.19 富士ゼロックス, Yahoo!, パナソニック　追記　20190115  夕
ver. 0.20 エンルート 追記 20190115 夜
ver. 0.21 「特許調査と製造業とIT企業の提携に焦点を絞っている理由」追記 20190116　朝
ver. 0.22 ALBERT 追記 20190116 午前
ver. 0.23 はじめに、おわりに再構成 20190117 
ver. 0.24 ロビット otuA（オチュア）追記 20190213
ver. 0.25 「量子アニーリングの基礎」を読む　追記 20190718
ver. 0.26 参考資料追記 20201226
ver. 0.27 データサイエンティストの気づき『勉強だけして仕事に役立てない人。大嫌い』それ自分かもってなった。20210918
http://b.hatena.ne.jp/guide/bbutton
<a href="http://b.hatena.ne.jp/entry/s/qiita.com/kaizen_nagoya/items/fbe846de16f74bea1d6f" class="hatena-bookmark-button" data-hatena-bookmark-layout="basic-label-counter" data-hatena-bookmark-lang="ja" title="このエントリーをはてなブックマークに追加"><img src="https://b.st-hatena.com/images/entry-button/button-only@2x.png" alt="このエントリーをはてなブックマークに追加" width="20" height="20" style="border: none;" /></a><script type="text/javascript" src="https://b.st-hatena.com/js/bookmark_button.js" charset="utf-8" async="async"></script>
### 最後までおよみいただきありがとうございました。
いいね　💚、フォローをお願いします。
####  Thank you very much for reading to the last sentence.
Please press the like icon 💚　and follow me for your happy life.
