---
layout: post
title: "ゲームリリースプラットフォーム　リリース要件"
date: 2024-01-01
categories: [create_game]
tags: []
thumbnail: "./images/2024-01-29-13-32-40.png"
---

<img src="{{ './images/2024-01-29-13-32-40.png' }}" alt="image" width="250" class="center-image"/>
  

<br>

## Google Play Console
[Developers Console Help](https://support.google.com/googleplay/android-developer/answer/9866151?hl=ja#zippy=%2C%E7%B0%A1%E5%8D%98%E3%81%AA%E8%AA%AC%E6%98%8E)
#### ■アプリアイコン
- 32 ビット PNG（アルファ付き）  
- サイズ: 512 px x 512 px  
- ファイルの最大サイズ: 1,024 KB  
  

#### ■説明
- 半角 80 文字（全角 40 文字）以内  

#### ■フィーチャー グラフィック
- JPEG または 24 ビット PNG（アルファなし）
- サイズ: 1024 px x 500 px


#### ■スクリーンショット
- 2～8 枚のスクリーンショット
- スクリーンショットは、PNG または JPEG
- スマホの場合、縦横がそれぞれ 320～3,840 px
- 1,080～7,680 ピクセルのスクリーンショット
- 横向きの場合は 16:9、縦向きの場合は 9:16 のアスペクト比


#### ■プレビュー動画
- 動画の YouTube URL を使用
- YouTube の再生リストやチャンネルの URL は使用しない
- YouTube URL にタイムコードなどのパラメータを追加しない
- 動画の短縮リンクではなく YouTube 動画の完全なリンクを使用  
  - 使用可: https://www.youtube.com/watch?v=yourvideoid  
  - 使用不可: https://youtu.be/yourvideoid  
  
  
<br>
  
## iOS
### ■動画
※なんか公式ページの情報と違う気がする。
1920px x 886px　か　886px x 1920px
フレームレート30?
60だとエラーになった。
15秒〜30秒の長さ。15秒より短いとエラーになる。

### ■スクリーンショット
#### iPhone 6.7 Display
- 4～10 枚のスクリーンショット
- 1290 x 2796px か 2796 x 1290px

#### iPhone 6.5 Display
- 4～10 枚のスクリーンショット
- 1242 x 2688px か 2688 x 1242px か 1284 x 2778px か 2778 x 1284px
- もしくはiPhone 6.7 Displayを流用することも可能

#### iPhone 5.5 Display
- 5～10 枚のスクリーンショット
- 1242 x 2208px か 2208 x 1242px

#### iPad
- 5～10 枚のスクリーンショット
- 2048 x 2732 か 2732 x 1242px

### ■その他
スクショで6.7サイズの1つの画像だけエラーになった。  
<img src="{{ './images/2024-02-07-10-00-42.png' }}" alt="image" width="250"/>
サイズ違いだけな5.5ではエラーにならないんですよね。おかしい。  


## リジェクトメモ
### iOS
アプリ名が違う。でリジェクト  
→痛恨のミス。  
　Xcodeで変えちゃうとUnity情報が上書きされちゃうよね。  
　Unity上で変えないと。


### Android
ユーザーデータ - アカウント削除要件: アカウント / データ削除の無効なリンクがデータ セーフティ フォームに記載されています