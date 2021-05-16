---
title:  Mendeleyを使った文献管理のTips
tags:
  - Mendeley
  - research

---

Mendeleyは日本語文献の管理が苦手なので、ちょっとしたコツがいる。このエントリは随時加筆予定。

<!--more-->

<br>

#### 前提

- 日本語・英語両方の文献を読み、自らも日本語・英語両方の論文を書いている
- Mendeley Desktop を入れておく
- Mendeley の容量制限を回避するため（大学を出てからも使えるように）、 Preferences → Watched folders で、文献ファイルを Dropbox などのクラウドストレージ上のフォルダを指定する（以下、ここを「保存フォルダ」と呼ぶ）
- Preferences → File Organizer → Rename document files を有効にして適当に設定しておくと、PDFの管理が楽になる

<br>

#### 英語論文の取り込み

- 英語論文（しかもメジャーな雑誌）であればとても楽
- DLしたPDFを保存フォルダへ移動する。するとMendeleyが自動判別してテキトーなファイル名にrenameされる
- Mendeley Desktop で該当論文を開き Details を確認。DOIを入力して（PDFから既に取り込まれていることが多い）右側の検索ボタンから文献データを再検索させると、間違いのない情報に更新される（併せて、PDFファイル名も更新される）
  <br><br>
  <div align="center"><img src="https://i.gyazo.com/ab7f4ee3fdfabc7b168f60eb3f6abbe7.png" alt="search DOI" width="400"/></div>

<br>

#### 日本語論文の取り込み

- 基本的には英語論文と同じ流れで追加するが、[J-STAGE](https://www.jstage.jst.go.jp/browse/-char/ja/)が付与しているDOIはMendeleyで読み込むことができない（自分が試してきた限り）
- RISをDLして、 Mendeley Desktop → File → Import → RIS で先に文献情報だけつくっておく
- つくった文献情報に別途DLしたPDFを紐付けて保存する
- 英語論文で引用したいとき（英文タイトル、著者、雑誌名）は、英語標記だけを入れた文献データを別途つくっておく
  <br><br>
  <div align="center"><img src="https://i.gyazo.com/98281d123162beabf7503f8308820d1d.png" alt="download RIS" width="300"/></div>

<br>

#### 書籍情報の取り込み

- 書籍全体を引用するのか、それとも特定の章だけ引用するのかで使い勝手が変わる。今後も改善の余地あり
- 英語書籍全体を引用するなら、Googleスカラーの引用ボタンからbibtexなどを出力して読み込むのが手早いか？
  <br><br>
  <div align="center"><img src="https://i.gyazo.com/57365392a8f09c5742b6f60112f0c245.png" alt="import bibtex" width="300"/></div><br>
- 日本語書籍であれば、[CiNii 図書](https://ci.nii.ac.jp/books/)から「Mendeleyに書き出し」をするのが最も楽
  <br><br>
  <div align="center"><img src="https://i.gyazo.com/b33f5be6271cd090ec463af5cb877ce1.png" alt="Image from Gyazo" width="300"/></div>
