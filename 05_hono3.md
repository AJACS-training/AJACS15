[[AJACS15]]

&size(25){遺伝子発現データを使い倒す～R/&#66;ioConductor の導入と解析例～};　　　　担当：小野浩雅


~目次
#contents

# [[&size(20){Rとは};>https://biogps.gnf.org/]] [#t5ad14b0]
&color(green){フリーウェアでオープンソースのデータ解析環境};
- データの操作や計算、可視化のためのソフトが統合されたもの
- サンプルデータが豊富
- 対話的に実行可能
- Windows, MacOSX, UNIXとマルチプラットホームで動作

# [[&size(20){&#66;ioConductorとは};>http://www.bioconductor.org/]] [#t5ad14b0]
&color(green){生命科学分野のためのRパッケージプロジェクト};
- マイクロアレイデータなどの遺伝子発現プロファイルや質量分析データ、タンパク質相互作用データなどの解析パッケージ集

#  R/&#66;ioConductor の導入 [#f84e072d]
## 【実習】R/&#66;ioConductorのインストール [#j5a2d158]
- [[【使い方参考動画】>http://togotv.dbcls.jp/20090313.html#p01]]http://lifesciencedb.jp/image/small_video_icon.png
- 1. [[http://cran.r-project.org/bin/windows/base/>http://cran.r-project.org/bin/windows/base/]]を開きます。
- 2.トップにある[[「Download R 2.10.1 for Windows 」>http://cran.r-project.org/bin/windows/base/R-2.10.1-win32.exe]]をクリックして、インストーラ（R-2.10.1-win32.exe）をダウンロードします。
~ダウンロードが遅い場合は、[[http://dbcls.rois.ac.jp/~hono/R-2.10.1-win32.exe>http://dbcls.rois.ac.jp/~hono/R-2.10.1-win32.exe]]から落とせます。
- 3. インストーラのダウンロードが完了したら、インストーラを実行します。
- 4. インストールの設定画面が続きますが、基本的に初期設定でOKです。
- 5. インストールが完了すると、デスクトップに"R 2.10.1"のアイコンが作成されます。
- 6. アイコンをダブルクリックし、Rを起動します。
- 7. 続いて、Bioconductorをインストールします。
- 8.
 source("http://www.bioconductor.org/biocLite.R")
~と入力し、Enterを押します。（←コピペするとタイプミスがなくて良いです）
- 9. 続いて、　
 biocLite()　
~と入力し、Enterを押すとパッケージのインストールが始まります。
- 10. PCやネットワークの状況にもよりますが、この作業は5~10分ほど時間がかかるので、気長に待ちます。
- 11. 再び赤いカーソルが現れたら、インストール完了です。

#  R/&#66;ioConductor を用いた解析例 [#ja6c2ca1]
## 【実習】R/&#66;ioConductorを用いたマイクロアレイデータの正規化 [#sc9704ec]
### サンプルデータの用意 [#rcd264b1]
- [[皮膚の線維芽細胞からiPS細胞を作製したときのデータ>http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE18226]]を使用します。
- 生データは　ftp://ftp.ncbi.nlm.nih.gov/pub/geo/DATA/supplementary/series/GSE18226/GSE18226_RAW.tar　から取得可能です。

- マイクロアレイの生データの取得方法については統合TVの[[NCBI Gene Expression Omnibus (GEO)からマイクロアレイの生データをダウンロードする方法>http://togotv.dbcls.jp/20081218.html#p01]]を参照してください。

        --

- [[【使い方参考動画】>http://togotv.dbcls.jp/20090319.html#p01]]http://lifesciencedb.jp/image/small_video_icon.png
- 1. Rを起動します。
- 2. 「ファイル」の「ディレクトリの変更」をクリックして、マイクロアレイデータ（CELファイル）のあるフォルダを選択します。初期値のままならば「GSE18226_RAW」というフォルダです。
- 3.
 library(affy)
~と入力し、解析パッケージを読み込みます。
- 4. 続いて、
 write.exprs(justRMA(), file="RMA_expression.txt")
~と入力します。少々時間がかかりますが、しばらくそのままで待ちます。何もエラーメッセージが出なければ、RMAで正規化されたデータがタブ区切りのテキストファイル（RMA_expression.txt）として保存されます。
- 5. 次に、　
 write.exprs(mas5(ReadAffy()), file="MAS5_expression.txt")　
~と入力します。MAS5による正規化はRMA以上に時間がかかると同時に、大量のメモリを消費するのでマシン環境によってはエラーが出ることがあります。同様に何もエラーが出なければ、MAS5で正規化されたデータがタブ区切りのテキストファイル（MAS5_expression.txt）として保存されます。
- 6. さらに　
 write.exprs(mas5calls(ReadAffy()), file="MAS5calls_expression.txt")　
~と入力します。MAS5の Present / Absent コールがタブ区切りテキスト（MAS5calls_expression.txt）で保存されます。



## 【実習】R/&#66;ioConductorを用いたヒートマップの作成 [#de13b465]
### Rを使ったマイクロアレイデータの解析 [#k1f920a4]
- [[東京大学大学院農学生命科学研究科の門田幸二さん>http://www.iu.a.u-tokyo.ac.jp/~kadota/]]が自身のHPで公開されている「[[(Rで)マイクロアレイデータ解析>http://www.iu.a.u-tokyo.ac.jp/~kadota/r.html]]」が非常に有用です。
- コピペで結果が出せるよう書かれていることに加え、それを実行できるサンプルデータも用意されています。
        --
- [[【使い方参考動画】>http://togotv.dbcls.jp/20091219.html#p01]]http://lifesciencedb.jp/image/small_video_icon.png
- 1. Rを起動します。
- 2. 今回は用意されているサンプルデータを使うので、[[GDS1096_best10_heart.txt>http://dbcls.rois.ac.jp/~hono/GDS1096_best10_heart.txt]]をダウンロード（右クリックして「名前を付けてリンク先を保存」してください。）し、先程使った「GSE18226_RAW」というフォルダに入れます。「ファイル」の「ディレクトリの変更」をクリックして、「GSE18226_RAW」フォルダを選択します。
- 3.
 library(stats)
~と入力しパッケージを読み込みます。

- 4. 続いて、
 data <- read.table("GDS1096_best10_heart.txt", header=TRUE, row.names=1, sep="\t", quote="")
~と入力しデータを読み込みます。
- 5. 次に、　
 colnames(data) <- substring(colnames(data), 8, nchar(colnames(data)))   　
~と入力すると、列ラベル中の最初の8文字分（つまり "Normal_"）を削除することができます。
- 6. さらに　
 png(filename="heatmap.png")　
~と入力しヒートマップを出力する準備をしておきます。
- 7. そして　
 heatmap(as.matrix(data), Rowv =NA, Colv=NA, scale="row", col = cm.colors(100), main="Heart-specific genes (Best 10)", xlab="Tissue", ylab="Clone ID", margin=c(8,10))　
~と入力しヒートマップをイメージを作成します。
- 8. 最後に　
 dev.off()　
~と入力し作成されたヒートマップをheatmap.pngファイルとして出力します。

## その他のマイクロアレイデータ解析 [#kd4ab0fd]
門田さんの「[[(Rで)マイクロアレイデータ解析>http://www.iu.a.u-tokyo.ac.jp/~kadota/r.html]]」にさまざまなマイクロアレイの解析方法が紹介されてますので、このページを参考にしつつ、自分のやりたい解析をやってみましょう。
