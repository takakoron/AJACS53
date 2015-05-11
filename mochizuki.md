# AJACS御茶ノ水 DDBJ Pipelineを用いたDNA多型注釈解析の実習

国立遺伝学研究所 大量遺伝情報研究室  
[望月孝子](http://researchmap.jp/Takako.M/) tm@nig.ac.jp  
2015年5月20日 AJACS御茶ノ水@東京医科歯科大学


----

これは統合データベース講習会 御茶ノ水「DDBJ Pipelineを用いたDNA多型注釈解析の実習」の資料です。  
講習会全体のプログラムは[こちら](http://events.biosciencedbc.jp/training/ajacs53)です。  

----

## 概要

本講習は、DDBJ Read Annotation Pipeline (DDBJ Pipeline) を使用して、新型シーケンサ配列のアーカイブデータベース (DDBJ SRA) の 全ゲノム配列をリファレンスゲノムにマッピング、リファレンスゲノムとの配列比較からDNA多型の検出、そして、検出されたDNA多型に既知遺伝子アノテーションの注釈を行います。

----

## 講習の流れ
今回の講習では、コンピュータを使って以下の内容について説明します。

【実習】
- DDBJ Pipeline 基礎処理部 (https://p.ddbj.nig.ac.jp/) にてDDBJ SRAの公開データのインポート、マッピング
- DDBJ Pipeline 高次処理部 p-galaxy (https://p-galaxy.ddbj.nig.ac.jp) にてDNA多型の検出、既知遺伝子注釈

----

##### 講習に際しての注意とお願い

- みんなで同時にアクセスするとサイトにつながりにくくなることが予想されます。
    - サイトの反応が悪い時はタイミングをずらして実行してみてください。
    - 反応が無いからと言って何度もクリックするとますます繋がらなくなってしまいます。おおらかな気持ちで臨みましょう。
- わからないことがあったら挙手にてスタッフにお知らせください。
    - 遠慮は無用です(そのための講習会です!)。おいてけぼりは楽しくありません。

----

##### 実習を始める前に
 
- DDBJ Read Annotation Pipeline とは
    - [DDBJ Pipeline 基礎部](http://https://p.ddbj.nig.ac.jp)
	- [DDBJ Pipeline 高次処理部](https://p-galaxy.ddbj.nig.ac.jp/)
	 [![Gyazo](https://i.gyazo.com/37af6d0d753d3ab2430cb9a5be9e66c5.png)]
	
- DNApod: DNA Polymorphism AnnOtation Database とは   
    - [「DNApod」](http://tga.nig.ac.jp)
	 [![Gyazo](https://i.gyazo.com/thumb/200/_75ea5dcf078a81b2a2f35ca560d79925.png)]
　本日の講習はDNApod ワークフローの講習になります。

- DRAデータサーチ方法
    - [「DBCLS SRA Metadata Search」](http://sra.dbcls.jp/search)
	 [![Gyazo](http://i.gyazo.com/fab7f0ba81afbce32061692c344bf03f.png)](http://gyazo.com/fab7f0ba81afbce32061692c344bf03f)
  
----

####【実習】DNA多型注釈 DNApod ワークフロー 
- 本日の実習の流れ  

1. DDBJ Pipeline 基礎処理部へアクセスします。
　

2. DDBJ pipeline 基礎部へログインします。
　講習用のID と パスワードでログインしてください。
　ご自分のデータでの解析を行う場合は、アカウントを取得してください。  

3. クエリを選択します。
　今回の講習用データは、DRAの公開データを使用します。
　まず、DRAからデータインポートを行ってから、クエリデータを確認します。

4. マッピングツールを選択します。
　今回はbwaを使ってマッピングしていきます。
　各ツールの説明は、Tool名のリンクをクリックしてください。各Toolのwebサイトで確認することができます。


5. クエリセットを作成します。
　クエリに使用するRun accessionが複数ある場合、この機能を使用します。 
　今回はRun accessionが1つしかないので、あまり気にせず、セット作成を行って下さい。

6. リファレンスを指定します。
　今回の講習で使用する "Escherichia coli O157:H7 str. Sakai" のRefSeq ID

 [![Gyazo](http://i.gyazo.com/b60518629c6dd0fe8163776cc7824a3c.png)](http://gyazo.com/b60518629c6dd0fe8163776cc7824a3c)

7. 実行パラメータを設定します。

8. 実行条件の確認

 [![Gyazo](http://i.gyazo.com/78a17e8253cb9ed64f6becf96b5a1e03.png)](http://gyazo.com/78a17e8253cb9ed64f6becf96b5a1e03)

9. 実行結果の確認

10. 実行結果の確認　-詳細-

11. 高次処理部 (p-galaxy) へのアクセス
12. 高次処理部へのログイン

13.  ヒストリーの作成

14. 礎処理部のsamtools mpileupデータインポート

15. ホモSNPsの検出
 - [肝臓特異的遺伝子の検索結果一覧](http://refex.dbcls.jp/genelist.php?lang=ja&db=human&roku_valid=1&rk[31]=31&order_key=score)に移動して、3つの遺伝子を「リストに追加」してみましょう。
 - 追加した件数は「リストを見る」の横に表示されます。
 - 「リストを見る」をクリックするとリストに移動します。
 - 『並べて表示する』にチェックを入れて、「遺伝子を並べて表示」をクリックします。
 - 並列に比較することで見えてくる「違い」はなんでしょうか。

 [![Gyazo](http://i.gyazo.com/f832aab525efcbd99854b8c920be0fcf.png)](http://gyazo.com/f832aab525efcbd99854b8c920be0fcf)  
 [![Gyazo](http://i.gyazo.com/0c604ddeee80bf4adf14ce52876a5744.png)](http://gyazo.com/0c604ddeee80bf4adf14ce52876a5744)

16. SNPsアノテーション SnpEff DBダウンロード

17. SNPsアノテーション SnpEff

18. SNPsアノテーション SnpEff 出力ファイル (1)

19. SNPsアノテーション SnpEff 出力ファイル (2)

----

講習は以上です。
お疲れ様でした。

ご不明点があれば、pipeline_dev@ddbj.nig.ac.jp へお問い合わせください。
