# なでしこ用旧暦ライブラリ
　[日本語プログラミング言語「なでしこ」](https://nadesi.com/)で西暦と旧暦（和暦）を相互変換したりなんだりするもの。

　標準で使えるnakodate.dllの旧暦変換とは異なり、歴史上使用されていた実際の暦と合うよう文献データを元に変換するものです。
（一口に旧暦と言っても幾度も改暦が繰り返されており、人為的に操作が加えられている場合もあるため、天文学的な計算で算出するのは限界があります）

　現在取得できるデータの範囲は645/2/2(大化元年1月1日)から2099/12/31です。

　おまけで、旧暦や節切の干支、九星、六曜が取得出来ます。

　また、なでしこではできない紀元前の修正ユリウス日の取得や、修正ユリウス日から西暦への変換が出来ます。

## ファイル

- **Qreki.nako**

　　なでしこのインストールフォルダ内のlibフォルダに放り込むか、プログラムと同じ所に置いて、プログラムの先頭で取り込む。
 
```
!『Qreki.nako』を取り込む。
```
 
- **Qreki_data.json**
 
　　旧暦と元号のデータです。ありかを冒頭の「和暦データ」に指定。（libに突っ込む場合は、ランタイムパス）
 
 ```
 和暦データ＝「{ランタイムパス}/lib/Qreki_data.json」を開いて、それをJSONデコード。
 ```
 
- **Qreki_sample.nako**

　　サンプル。

## 旧暦データについて

### 旧暦表

　645(大化元)から2099(令和81)までの元日、閏、月の大小を表にしたもの。

- 「元日」は旧暦1/1の西暦日付。
- 「閏」は閏月がある場合その月番。
- 「大小」は、大の月1、小の月0の配列で、いわゆる大小暦になっています。

　大化元年から明治5年までは『日本暦日原典』を参照。また、『国立天文台 暦計算室』の計算結果の校訂を参照。

　明治6年以降については、なでしこの旧暦変換で作成。
 （なでしこの旧暦変換には問題がありましたが、朔の日付と閏については正しく取得されており、こちらのデータには問題ありません。旧暦変換で問題のあった日付について、正しい出力を確認しています）

　2033年問題については『暦文協』の見解に基づき閏11月案に修正。

### 元号一覧

　645(大化元)から2099(令和81)までの元号と改元日のリスト。元号未制定期間は天皇の年期を代用しています。

- 「和暦」は和暦での改元日。
- 「西暦」はそれを西暦に直したもの。
- 「開始」「終了」は元号未制定時期と南北朝の元号並立期間に関連した例外処理用。
- 「南北朝」は、その元号が南朝で使われたものか北朝で使われたものか。

### 参考
- 『日本暦日原典』　内田正男　雄山閣出版　463900091X
- 『国立天文台 暦計算室』　http://eco.mtk.nao.ac.jp/koyomi/
- 『こよみのページ』　http://koyomi8.com/
- 『暦文協』　https://www.rekibunkyo.or.jp/top.html

## おことわり

　CC0で公開していますので、自己責任で自由にご利用下さい。なでしことか関係なく、データだけ使ってもらっても構いません。

　旧暦の出力については十分確認したつもりですが、万一間違いがありましたらすみません。
 
　プログラムでもデータでも、間違いを発見されたら教えていただけると大変助かります☆
