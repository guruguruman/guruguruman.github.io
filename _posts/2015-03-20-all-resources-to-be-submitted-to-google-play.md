---
layout: post
title: "Google Play Store 必要メタデータ仕様まとめ"
description: "Google Playに提出すべきメタデータの仕様一覧"
category: Android
tags: [android, google play, smartphone, promotion]
---

## 1. アイテムの詳細


アイテムの詳細は、プロモーション上とても重要。12%のユーザーが毎日Google Play Storeで検索し、50%が週1で検索しているらしいです。つまり、検索から安定的に相当量のトラフィックが呼び込める可能性があります。

```
To follow up his statement, Jain reveals some Google Play search data for the first time. He said 12 percent of daily active users (DAU) search for apps daily, 50 percent of DAU search for apps weekly and Google sees six million unique phrases searched monthly.
```
引用元：[Google discloses how search for Google Play works for the first time; 12 percent of DAU search for apps daily](http://www.adweek.com/socialtimes/google-discloses-how-search-for-google-play-works-for-the-first-time-12-percent-of-dau-search-for-apps-daily/539639?red=im)

記述時に地雷を踏まないため、[アイテムの詳細を記述する上でのポリシーについて](https://support.google.com/googleplay/android-developer/answer/113474) は読んでおいたほうが良いと感じました。

### 1-A. タイトル

Google Play Storeにアプリのタイトルとして表示される。アプリの検索順位上昇、CTR上昇が狙えるとても重要なメタ情報。最大30文字。

### 1-B. 簡単な説明

最大80文字。

### 1-C. 詳細な説明

ストアで表示される説明文。最大4,000文字。


この項目では、HTMLタグの一部が使えるようなので、テキストに装飾を加えるのはCVRを上げる点で効果的だと思います。

```
Google Playの場合、<hn>／<b>／</a>／<font>などのHTMLタグが利用でき、見出を目立たせたり、強調文字の色を変えたり、リンクを張ったりできます。
```
引用元：[Androidアプリ制作者必見！本気でGoogle Playの検索順位を上げるための、13のランキングアップ術](http://www.find-job.net/startup/factor-of-google-play-ranking)


## 2. 画像アセット


画像アセットの全体観を掴むためには、[アプリの機能を紹介するスクリーンショットや動画について](https://support.google.com/googleplay/android-developer/answer/1078870)を読むのが役に立つと思います。

特に画像アセットのうち、スクリーンショットの準備に時間がかかると思います。電話用、タブレット用（7インチ・10インチ）を用意することが可能で、準備した場合それぞれ最適化されて表示されます。


### 2-A. スクリーンショット：電話用

タブレット以外の電話端末向けスクリーンショット。こちらの解像度は`640×1136`か`750×1334`が良いと思います。特に指定がないのと、iOS版とのリソース共用のためです。

また、守るべき要件として下記4つが用意されています。これらに反するスクリーンショットを用意してはならないです。これは電話用スクリーンショットだけではなく、後述するタブレット用スクリーンショットでも同じです。

- JPEG または 24 ビット PNG（アルファなし）
- 最小サイズ: 320 ピクセル
- 最大サイズ: 3840 ピクセル
- スクリーンショットの最大サイズを最小サイズの 2 倍以上にすることはできません。

#### 掲載イメージ

![image](https://storage.googleapis.com/support-kms-prod/SNP_FCD84192F36591CEB4F1237A19CCD8F76F7F_4509843_en_v2)

### 2-B. スクリーンショット：7インチ + 10インチ

タブレット用スクリーンショット。電話用に同じく厳密な規定はないですが、解像度は`1536×2048`で作成するのが良いと思います。なぜなら、後述するように推奨解像度が`1280 x 720以上`なのと、こちらもiPad、iPad Miniとリソースが共用できるからです。

#### タブレット用スクリーンショットを用意する理由

タブレットの検索流入を最大化するには「タブレットに最適化」する必要があります。タブレットのGoogle Play Storeで検索した際の露出が増加が見込めるからです。

アプリの掲載情報を「タブレットに最適化」するためには、タブレット用のスクリーンショットを少なくとも1つずつアップロードする必要があります。
「タブレットに最適化」する理由は、検索時にデフォルトで「タブレットに最適化」されたアプリを検索結果に表示する事にあります。検索画面でフィルタを変更しないと「すべてのアプリ」が表示されません。タブレットに最適化されていないアプリに関しては、「スマホ向け」というようなラベル表示がつくようになってしまいます。

```
- Show the core functionality of your app, not a startup or sign-in page. Wherever users will spend most of their time, that's what you should show in your screenshots.
- Add screenshots taken on both 7-inch and 10-inch tablets.
- Add screenshots taken in both landscape and portrait orientations, if possible.
- Use screen captures if possible. Avoid showing actual device hardware in your screenshots.
- The recommended resolution of your tablet screenshots is 1280 x 720 or higher in each orientation.
- Upload as many as 8 screenshots of your tablet UI for 7-inch tablets and an additional 8 for 10-inch tablets.
```
引用元：[Tablet App Quality - 11. Showcase Your Tablet UI in Google Play](http://developer.android.com/distribute/essentials/quality/tablets.html#google-play)

この引用でGoogleが書いている項目で重要な点は「1280 x 720 以上の解像度を期待している」ことだと思います。最低限、解像度は守れば良いと思います。


### 2-C. 高解像度アイコン（512 x 512）

高解像度アイコンは、Google Play Store上の様々な場所で利用される。特にストアのアプリの検索一覧やランキングなどで表示されるので、かなり重要。

#### 利用イメージ
![image](https://storage.googleapis.com/support-kms-prod/SNP_58239E7DEB1B96C3C9E75D607C6178026F04_4509860_en_v2)

### 2-D. 宣伝用画像（1,024 x 500）

宣伝用画像は「Google Play Store」の「ストアの掲載情報」ページの上部に表示されます。そのため、アピール力の強い画像であるべきです。また、宣伝用画像は必須であり、ストアの掲載情報に変更を加えるには宣伝用画像を提出する必要があります。

- アセットの枠線の近く、特にフレームの下部 3 分の 1 の範囲近くにはコピーや重要なビジュアル情報を含めないでください。
- フレームの垂直と水平の中心でロゴやコピーの情報を中央揃えにしてみてください。
- テキストを追加する場合は、大きいサイズのフォントを使用してください。
- 画像はアプリアイコンとは別に単独で表示されることがあります。

Googleの推奨する宣伝用画像の要件は上の4つ。これらに準拠しないと即BANを食らうわけではないと思いますが、準拠したほうが良いと考えます。

参考：[宣伝用画像について（英語）](http://android-developers.blogspot.jp/2011/10/android-market-featured-image.html)

#### 利用イメージ

![image](https://storage.googleapis.com/support-kms-prod/SNP_0EB3F1E9CE8FBE0055660FF66D7438F25CB7_6071289_en_v0)

### 2-E. プロモーション画像（180 x 120）※任意

古いバージョンの Android OS（4.0 より前）でのプロモーションに使用します。この画像がなくても、ストアの掲載情報の更新を送信することは可能です。
