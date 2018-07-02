DNAデータベース総覧と検索、MiGAP、アナトモグラフィー／BodyParts3Dの使い方
        --
目次

#contents
        --
[[統合ホームページ>http://lifesciencedb.jp/]]中の項目でアイコン（これ→ http://lifesciencedb.jp/image/small_video_icon.png ）があるサービスは統合TVの動画による説明があります。実際に使う前に是非ご覧ください。

#  [[MiGAP>http://migap.lifesciencedb.jp/]] [#o6ce55e3]
微生物ゲノム解析において定評あるデータベースと定評あるアルゴリズムを組み合わせたアノテーション実行パイプライン。このサービスを使うためにはOpenIDが必要なのでまず取得します。

http://lifesciencedb.jp/image/small_video_icon.png [[統合DBを使い倒すためにOpenIDを取得する>http://togotv.dbcls.jp/20080507.html]]

取得できた方から[[チュートリアル>http://migap.lifesciencedb.jp/mgap/help/1/2/MiGAP_01.ja.pdf]]に沿ってやってみましょう。

#  [[アナトモグラフィー／BodyParts3D>http://lifesciencedb.jp/ag]] [#obb3d57e]
解剖学用語を選択して自由に人体のモデル図(アナトモグラム)を描くツール。

http://lifesciencedb.jp/image/small_video_icon.png [[オンライン人体地図サービス「アナトモグラフィー」を使い倒す 2008秋>http://togotv.dbcls.jp/20080927.html]]

[[アナトモグラフィーのヘルプ>http://lifesciencedb.jp/ag/help/]]を参考に気になる臓器（例えば心臓）を表示し、いじってみましょう。

##  蛇足 [#bf3a02c3]
今流行りのtwitterからもアナトモグラフィーは利用可能です。アカウント名[[body3d>http://twitter.com/body3d]]に対してつぶやいてみましょう（例えば「はい」）。

# [[DNAデータベース総覧と検索>http://lifesciencedb.jp/ddbj/]] [#n7e4b94d]
DDBJ/EMBL/GenBank（DNA塩基配列のデータベース）に登録されている全レコードをプロジェクト単位で分類。「生物種」と「研究の型」の二次元で分類。データを一括ダウンロード可能。

- 【実習1】「生物群区分」で特定のカテゴリーを選ぶと、研究プロジェクト数が絞り込まれることで数が変化する。「生物群区分」で「ヒト」を選ぶ前と後で「研究の型別分類」の「機能RNA・RNAゲノム」の項目はいくつからいくつに変化するか？
- 【実習2】「生物群区分」で「ヒト」、「研究の型別分類」で「mRNA」を選んで得られる研究プロジェクトのリストを、「研究プロジェクトの一覧」を「サイズ順」にすることでデータサイズの大きなプロジェクト順に並び替えなさい。トップ３にランキングされる研究プロジェクトはそれぞれ何か？
    - 【参考】[[DDBJ のデータ公開形式 (flat file) の説明>http://www.ddbj.nig.ac.jp/sub/ref10-j.html]]
- 【実習3】統合ホームページ中の「ダウンロード」のタブをクリックすると、国内のゲノム・ポストゲノムプロジェクト配列データのダウンロードページに辿り着ける。この中から興味のあるプロジェクトを選び（例えば、シロイヌナズナ (Riken2004年)）、公開されている配列をFASTA形式で一括ダウンロードしなさい。
- 【応用1】上の実習でわずか数クリックで実現した一括ダウンロードできることのメリットは何だろうか？それがない場合、どういった手続きをしないといけないかを考えてみなさい。

http://lifesciencedb.jp/image/small_video_icon.png [[DNAデータベース総覧と検索を使い倒す>http://togotv.dbcls.jp/20080514.html]]

#  発現データとしての配列データ [#g5acd6a5]
[[EST(Expressed Sequence Tags)>http://allie.dbcls.jp/cgi-bin/search.cgi?key=EST]]に対しては、遺伝子に対応づけて、それぞれごとに&size(24){出現回数を数え上げることで発現データと見なすことができる};。ESTは、DDBJ/EMBL/GenBankのDivisionの一つとなっており、その中身を検索し閲覧するサービスがDDBJ/DBCLSで公開されている。

#dwrite(){{
<img border="3" src="http://motdb.dbcls.jp/?plugin=attach&pcmd=open&file=ProjectE.010.png&refer=AJACS10/bono2" alt="遺伝子発現データ">
```

##  [[Bodymap-XS>http://bodymap.jp/]] [#t8951966]
分類学と解剖学による動物のESTカウント数データの統合サイト。
- 【実習4】表の横軸は各生物種、縦軸は臓器であるが、'expand'をクリックするとさらに臓器は細かい一覧となる。その中から'kidney'（腎臓）を見つけ、ヒトのカラムにある二種類（黒色と緑色）の数字をクリックしてみよ。それぞれ何のデータであっただろうか？
- 【実習5】ヒトのkidneyのESTのカウント数をクリックしたときに現れる遺伝子一覧でkidney specific（腎特異的）な発現パターンを示していると考えられる遺伝子を3つ選定しなさい。同様にconstitutive（構成的）な発現パターンのものも3つ選びなさい。
- 【実習6】orthologカラムにある数字をクリックすることでその遺伝子のオーソログ遺伝子の発現パターンが一望出来る。上で選んだ複数の遺伝子についてそれぞれのオーソログ遺伝子の発現パターンを閲覧し、発現パターンについても保存されているかどうか、確認しなさい。なお、orthologカラムに数字がない場合は Homology search カラムにある'search'ボタンを用いて相同な遺伝子をBLAST検索してみなさい。

http://lifesciencedb.jp/image/small_video_icon.png [[Bodymap-XSを使い倒す>http://togotv.dbcls.jp/20090210.html]]

##  [[植物ESTボディーマップ>http://lifesciencedb.jp/bodymap-plant/]] [#uf67137e]
植物の各臓器、組織における遺伝子の発現量をESTを使って推定したデータベース。

http://lifesciencedb.jp/image/small_video_icon.png [[植物ESTボディーマップを使い倒す>http://togotv.dbcls.jp/20090328.html]]


##  [[ヒト統合ボディーマップ>http://okubolab.genes.nig.ac.jp/bodymap_i/]] [#o9e5b91e]
5種類のヒト発現データ (iAFLP, Affymetrix GeneChip, EST, SAGE-NCBIのタグマップ, SAGE-大久保研独自タグマップ)に対して対応するNCBIのUniGene(ユニジーン)でデータを整理。対象生物種はヒトのみだが、複数の手法による客観的な遺伝子発現データの比較が可能。

http://lifesciencedb.jp/image/small_video_icon.png [[ヒト統合ボディーマップ 1.発現パターンから探す>http://togotv.dbcls.jp/20090204.html]]

http://lifesciencedb.jp/image/small_video_icon.png [[ヒト統合ボディーマップ 2.染色体領域で眺める、他>http://togotv.dbcls.jp/20090218.html]]


# [[遺伝子発現バンク(GEO)目次>http://lifesciencedb.jp/geo/]] [#n7e4b94d]
NCBIの[[GEO>http://www.ncbi.nlm.nih.gov/projects/geo/]]（Gene Expression Omnibus:mRNA発現情報のデータベース）に登録されている全レコードをプロジェクト単位で分類。「生物種」、「研究の型」、「部位」の三次元で分類。データを一括ダウンロード可能。

http://lifesciencedb.jp/image/small_video_icon.png [[遺伝子発現バンク(GEO)目次を使い倒す－その壱>http://togotv.dbcls.jp/20080623.html]]

ここから先の、GEOでのデータの解析方法については、[[「遺伝子発現データベースを使い倒す」>../hono2]]にて詳しく紹介する。
