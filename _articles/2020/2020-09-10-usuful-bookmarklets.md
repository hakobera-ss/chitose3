---
title:  植物屋的に便利なブックマークレット集
tags:
  - plant
  - JavaScript

---

ワンクリックで植物の和名から学名を検索したかったので、ついでにいろいろつくってみた。

<!--more-->
<br>

## 元のブックマークレットと参考記事

これをブラウザにブックマークし、検索ワードを選択した状態でブックマークレットを押下するとGoogle検索の結果が別タブで表示される。（もっとも、大抵のブラウザは右クリックして出てくるメニューから検索ができるはずなので、このブックマークレット自体を使うメリットは薄い）

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='http://www.google.co.jp/search?hl=ja&q='+encodeURIComponent(Q)+'&lr=lang_ja';y.open(m,'_blank','');%7D)();
```

これをブックマークした際に参考にしたサイトが閉鎖してしまっていたので、おそらく同様の記載がある記事を挙げておく。

[Bookmarklet](https://sites.google.com/site/bookmlt69/)

<br>

JavaScript の素人ながら、上記コードの後半にある`+encodeURIComponent(Q)+`の前後を入れ替えれば任意の検索窓のあるサイトへアクセスできると推測できるので（もし間違ってたらこっそり教えて下さい）いろいろ作成した。

<br>

## 国内のサイト

<br>

#### YList

日本産維管束植物の和名・学名を検索できる。ほぼ毎日お世話になっているので、検索窓を表示させる手間すら惜しくなったのが今回のきっかけ。

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='http://ylist.info/ylist_simple_search.php?any_field='+encodeURIComponent(Q)+'&capital=0&family_order=2&family_disp_type=1&family_header=0&spec_order=0&list_type=0&search=%E6%A4%9C%E7%B4%A2';y.open(m,'_blank','');%7D)();
```

<br>

#### 日本のレッドデータ検索システム

日本のレッドリスト掲載種（環境省＆各都道府県）を横断検索する。

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='http://jpnrdb.com/search.php?mode=key&q='+encodeURIComponent(Q);y.open(m,'_blank','');%7D)();
```

<br>

#### iNaturalist

世界中の生物の観察記録をSNSのように共有・同定しているサイト。分布とか各言語の名称を調べるには便利（ただし情報の信頼性は Wikipedia 相当）。 California Academy of Sciences と National Geographic Society が共同運営しているが、日本語対応もしているのでこっちに区分しておく。

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='https://www.inaturalist.org/search?q='+encodeURIComponent(Q);y.open(m,'_blank','');%7D)();
```

<br>

## 海外のサイト

<br>

海外のサイトなので、学名で検索する。あと、命名者や ssp., var. などを挟むと検索エラーになるので注意。

<br>

#### Plants of the World Online

Kew Garden が運営していて、世界の維管束植物の情報を検索できる。日本産植物の情報は古いことも多いが、国際的な信頼は高い。なお、[DuckDuckGo](https://duckduckgo.com)では`!plants`コマンドで同様の検索ができる。

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='http://plantsoftheworldonline.org/?q='+encodeURIComponent(Q);y.open(m,'_blank','');%7D)();
```

<br>

#### eFloras.org

世界各国の植物誌を横断検索できる。Flora of China の検索によく使う。ちなみに [Flora of Japan](https://www.kspub.co.jp/book/series/S165.html) は1993年から刊行が始まり、未だ未完の書……（せめて終わった分だけでもオンライン公開してくれ！！）

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='http://www.efloras.org/browse.aspx?flora_id=0&name_str='+encodeURIComponent(Q)+'&btnSearch=Search';y.open(m,'_blank','');%7D)();
```

<br>

#### Catalogue of Life checklist (Beta)

世界中の全生物の学名を検索できる。異名関係のチェックによく使う。なぜか編纂に日本人が関わっていないので、大学紀要とかで新種記載された種は、漏れているか異名の順番が逆にされてしまっていることも多い。

今年からサイトが[改修され始めた](https://github.com/CatalogueOfLife/general)ので、API含め諸々が変わる可能性がある。

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='http://www.catalogueoflife.org/col/search/all/key/'+encodeURIComponent(Q)+'/fossil/1/match/1';y.open(m,'_blank','');%7D)();
```

<br>

#### Global Biodiversity Information Facility

日本語では「地球規模生物多様性情報機構」。学名から分布図とか標本画像を調べるのに便利。世界中の大学・博物館から提供された情報がベースになっているが、前述のiNaturalistなど民間のデータもここに集約される。また、分類体系は Catalogue of Life に基づいている。

```javascript
javascript:(function()%7Bx=document;y=window;if(x.selection)%20%7BQ=x.selection.createRange().text;%7D%20else%20if%20(y.getSelection)%20%7BQ=y.getSelection();%7D%20else%20if%20(x.getSelection)%20%7BQ=x.getSelection();%7D;m='https://www.gbif.org/ja/search?q='+encodeURIComponent(Q);y.open(m,'_blank','');%7D)();
```
