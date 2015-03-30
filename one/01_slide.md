!SLIDE 
# OpenCVいじってみた #

!SLIDE bullets incremental
# もくじ #

* OpenCVって何さ？
* オブジェクト検出
  + 機械学習
  + オブジェクト検出器
  + 検出してみよう
* 何に使おうか？
  + 笑い男ごっこ（俺の目を盗んだな）
  + I am ぼるだりんがー

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
## オブジェクト検出の流れ
### 機械学習

![](http://image.gihyo.co.jp/assets/images/dev/feature/01/opencv/0003/thumb/TH400_01.png)

!SLIDE commandline incremental small 

    $ createsamples -info OK.txt -vec pos_output.vec -num 4000 -bgcolor 255 -w 44 -h 18
    $ haartraining.exe -data gihyo_logo -vec output.vec -bg NG.txt -npos 4000 -nneg 1685 -w 44 -h 18 -mode ALL


                         ／）
                      ／／／）
                   ／,.=ﾞ''"／
      ／         i f  ,.r='"-‐'つ＿＿＿_      こまけぇこたぁいいんだよ！！
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

XMLです(嫌な思い出)
使います(Rubyで)

@@@ruby



!SLIDE
### 検出してみよう



!SLIDE bullets
  * 機械学習
