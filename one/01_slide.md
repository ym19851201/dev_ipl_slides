!SLIDE subsection
# OpenCVいじってみた #

!SLIDE bullets incremental
# もくじ #

* OpenCVって何さ？
* オブジェクト検出
  + 機械学習
  + オブジェクト検出器
* 何に使おうか？
  + 笑い男ごっこ（俺の目を盗んだな）
  + I am ぼるだりんがー
  + うちの子(ランバ・ラル)検出

!SLIDE smaller
# OpenCVって何さ？

* 線形代数や統計処理など，コンピュータビジョンに必要な各種数学関数
* 直線や曲線，テキストなど画像への描画関数
* OpenCVで使用したデータを読み込み/保存するための関数
* エッジ等の特徴抽出や画像の幾何変換，カラー処理等々の画像処理関数
* 物体追跡や動き推定などの動画像処理用関数
* 物体検出などのパターン認識関数
* 三次元復元のためのカメラ位置や姿勢の検出などのカメラキャリブレーション関数
* コンピュータにパターンを学習させるための機械学習関数
* 画像の読み込みや保存，表示，ビデオ入出力などインターフェース用関数

!SLIDE small

                         ／）
                      ／／／）
                   ／,.=ﾞ''"／
      ／         i f  ,.r='"-‐'つ＿＿＿_      こまけぇこたぁいいんだよ！！
    /           /      _,.-‐'~／⌒    ⌒＼
        ／     ,i      ,二ﾆ⊃（ ●）.  （●）＼
      /       ﾉ       ilﾞフ::::::⌒（__人__）⌒::::: ＼
            ,ｲ｢ﾄ､    ,!,!|          |r┬-|          |
          /  iﾄヾヽ_/ｨ"＼         `ー'´       ／


## 結局何がしたいって画像認識だしね

!SLIDE subsection
# オブジェクト検出 #

!SLIDE
## オブジェクト検出の流れ
* サンプル作成
* 機械学習によって検出器作成
  ![](http://image.gihyo.co.jp/assets/images/dev/feature/01/opencv/0003/thumb/TH400_01.png)
* 検出器を使って目的のオブジェクトを検出

!SLIDE small
# サンプル作成と機械学習

  ![](http://image.gihyo.co.jp/assets/images/dev/feature/01/opencv/0003/thumb/TH400_01.png)
<p><img src="http://image.gihyo.co.jp/assets/images/dev/feature/01/opencv/0004/thumb/TH250_03.png" alt="" height="250"></p>

!SLIDE small
# サンプル作成と機械学習

* OK.txt作らなきゃ
* [ObjectMarker](https://github.com/takmin/ObjectMarker)なるものがあるらしい
* ビルドできない(情弱)
* 作りゃいいじゃん(ｼﾞｬｯｳﾞｧで)  
  →GAIAで培ったMVCをガン無視する技術でGUIを作成  
  (現在MVCに則って改造中)


!SLIDE commandline incremental small 

## 作成したOK.txtでサンプル作成からの機械学習

    $ createsamples -info OK.txt -vec pos_output.vec -num 4000 -bgcolor 255 -w 44 -h 18
    $ haartraining.exe -data hoge -vec output.vec -bg NG.txt -npos 4000 -nneg 1685 -w 44 -h 18 -mode ALL


                         ／）
                      ／／／）
                   ／,.=ﾞ''"／
      ／         i f  ,.r='"-‐'つ＿＿＿_      コマンド打ちゃあいいんだよ！！
    /           /      _,.-‐'~／⌒    ⌒＼
        ／     ,i      ,二ﾆ⊃（ ●）.  （●）＼
      /       ﾉ       ilﾞフ::::::⌒（__人__）⌒::::: ＼
            ,ｲ｢ﾄ､    ,!,!|          |r┬-|          |
          /  iﾄヾヽ_/ｨ"＼         `ー'´       ／


＿人人人人人人人人人人人人人人人人人＿  
＞　めっちゃ時間かかるけどな！！！　＜  
￣Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y￣  


!SLIDE
## オブジェクト検出器

さっきめっちゃ時間かけて作ったXMLのことです(嫌な思い出)  
使います(Rubyで)  

    @@@ruby
    a = 'aaa'



!SLIDE subsection
# 何に使おうか？
## ~笑い男ごっこ編~

!SLIDE
さっきめっちゃ時間かけて作った検出器ではないものを使って顔検出  
(だって顔検出器OpenCVに入ってんだもん)  
→笑い男になれる！

<p><img src="http://bronzeback.cocolog-nifty.com/photos/uncategorized/2007/09/27/laughingman_2.gif" alt="" width="200" height="200"></p>

!SLIDE execute
## これであなたも笑い男


    @@@ruby
    %w{a b c d e}.each do |e|
      e + "xxx"
    end

!SLIDE subsection
# 何に使おうか？
## ~ボルダリング編~

!SLIDE subsection
# 何に使おうか？
## ~ランバ・ラル編~
