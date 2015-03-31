!SLIDE subsection
# オブジェクト検出 #

!SLIDE small
# オブジェクト検出の流れ
* サンプル作成
  + 画像を集める
* 機械学習によって検出器作成
  + マシンに頑張ってもらう

  ![](http://image.gihyo.co.jp/assets/images/dev/feature/01/opencv/0003/thumb/TH400_01.png)


* 検出器を使って目的のオブジェクトを検出

!SLIDE small
# サンプル作成と機械学習

<p><img src="http://image.gihyo.co.jp/assets/images/dev/feature/01/opencv/0004/thumb/TH250_03.png" alt="" height="500"></p>

!SLIDE small
# サンプル作成と機械学習
## NG.txt

<div class="txt">
./NG/image_001.jpg<br>
./NG/image_002.jpg<br>
./NG/image_003.jpg<br>
.<br>
.<br>
.<br>
</div>

## OK.txt

<div class="txt">
./OK/image_001.jpg 3 0 0 50 50 32 45 20 30 44 78 5 30<br>
./OK/image_002.jpg 2 30 47 39 49 40 55 19 28<br>
./OK/image_003.jpg 1 0 0 30 30<br>
.<br>
.<br>
.<br>
</div>

!SLIDE small
# サンプル作成と機械学習
## OK.txt作らなきゃ

* [ObjectMarker](https://github.com/takmin/ObjectMarker)なるものがあるらしい
* ビルドできない(情弱)
* 作りゃいいじゃん(ｼﾞｬｯｳﾞｧで)  
  →GAIAで培ったMVCをガン無視する技術でGUIを作成  
  (現在MVCに則って改造中)


!SLIDE commandline incremental small 

## 作成したOK.txtでサンプル作成からの機械学習

    $ createsamples -info OK.txt -vec output.vec -num 4000 -bgcolor 255 -w 44 -h 18
    $ haartraining -data hoge -vec output.vec -bg NG.txt -npos 4000 -nneg 1685 -w 44 -h 18 -mode ALL


<div class="aa">
　　　　　　　　　　　　 ／）<br>
　　　　　　　　　　　／／／）<br>
　　　　　　　　　 ／,.=ﾞ''"／<br>
　　　／　　　　 i f　,.r='"-‐'つ＿＿＿_　　　　　コマンド打ちゃあいいんだよ！！<br>
　　/　　　　　 /　　　_,.-‐'~／⌒　　⌒＼<br>
　　　　／　 　,i　　　,二ﾆ⊃（ ＞）.　（＜）＼<br>
　　　/　 　　ﾉ　　　 ilﾞフ::::::⌒（__人__）⌒::::: ＼<br>
　　　　　　,ｲ｢ﾄ､　　,!,!|　　　　　|r┬-|　　　　　|<br>
　　　　　/　iﾄヾヽ_/ｨ"＼ 　　 　 `ー'´ 　 　 ／<br>
<br>
</div>
<div class="aa" align="center">
＿人人人人人人人人人人人人人人人人人＿  <br>
＞　めっちゃ時間かかるけどな！！！　＜  <br>
￣Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y￣  <br>

</div>

