---
layout: post
title: "[プログラムメモ]スマホアプリの課金テスト"
date: 2024-01-09
categories: [プログラムメモ]
tags: []
thumbnail: "./images/2024-01-09-09-06-39.png"
---

スマホの課金テストメモです。  
自分の環境用ざっくりメモです。  
なので、あまり参考にしないでください。  
```※こうでも書かないと、記載ミスとかあった場合、「この記事で不具合が起こった」といちゃもんつけてくる人が  
過去1人だけですが、本当にいらっしゃったので。  ```

  
<img src="{{ './images/2024-01-09-09-06-39.png' }}" alt="image" width="250" class="center-image"/>

  
スマホアプリ作成時に課金テストで結構苦戦しました。  
次回も同じ箇所で詰まらないための自分用メモです。  
  
<br>

### iOS
iOSは簡単でした。  
簡単といえど、まずAppStoreConnectでアプリを作る必要があると思います。  
<br>
アプリ作成後、左メニューの「In-App Purchases」をクリック。  
<img src="{{ './images/2024-01-09-09-14-24.png' }}" alt="image" width="250" class="center-image"/>  
<br>
「＋」ボタンで課金アイテムを作っていきます。  
<img src="{{ './images/2024-01-09-09-15-08.png' }}" alt="image" width="250" class="center-image"/>  
<br>
PRODUCT ID、TYPE、課金額などを考慮。  
PRODUCT ID、TYPEはプログラムでの呼び出し時に利用すると思いました。  
  
あとは、テスト用アカウントの追加ですが、  
過去すでに作成しており、最新の作成方法は知らないのでここでは省きます。  
  
これでアプリのプログラム側を設定すれば、課金アイテムをテスト環境で確認できます。  
アプリはXcodeから実行したもので確認可能です。  
  
<br>
<br>

### Android
こちらが大変でした。  
こちらでもGooglePlayConsoleでアプリを作ります。  
<br>
作成後、左メニューの収益化より「アプリ内アイテム」をクリック。  
<img src="{{ './images/2024-01-09-09-42-40.png' }}" alt="image" width="250" class="center-image"/>  
<br>
「アイテムを作成」ボタンで課金アイテムを作っていきます。  
<img src="{{ './images/2024-01-09-09-43-14.png' }}" alt="image" width="250" class="center-image"/>  
<br>
アイテムID、価格などを考慮。  
後々、プログラムで利用すると思います。  
  
<br>
Androidの課金テストは内部テストで実施する必要があると思っています。
なので、アプリをGooglePlayConsoleにaabファイルをアップデートする必要があります。  
まず「内部テスト」をクリックします。  
押せない場合は設定が必要で、リリースに向けてアプリの設定が必要な場合があるかもです。  
<img src="{{ './images/2024-01-09-09-40-03.png' }}" alt="image" width="250" class="center-image"/>  
<br>
その後、アプリ設定やテスト設定を行い、「内部テスターに公開」状態になれば、配信OKだと思います。  
Androidについても、テスト用アカウントは昔に作成していまして、ここでは省きます。  
★UIがごちゃごちゃしているのか、ちょっと仕様が分かりにくいところがありました。
<img src="{{ './images/2024-01-09-10-00-40.png' }}" alt="image" width="250" class="center-image"/>  
<br>
公開後は、ここからも少し分かりにくいのですが、「テスター数」タブをタップ。  
<img src="{{ './images/2024-01-09-10-03-37.png' }}" alt="image" width="250" class="center-image"/>  
<br>
画面下の「テストへの参加方法」にて「リンクをコピー」でリンク先を保存します。  
<img src="{{ './images/2024-01-09-10-06-46.png' }}" alt="image" width="250" class="center-image"/>  
<br>
そのリンクをPCブラウザで開くと以下のページが表示されると思います。  
そのページにて「download it on Google Play」をクリックします。  
<img src="{{ './images/2024-01-09-10-08-12.png' }}" alt="image" width="250" class="center-image"/>  
<br>
以下ページが表示されますので、「Install on more devices」をクリックします。  
<img src="{{ './images/2024-01-09-10-11-24.png' }}" alt="image" width="250" class="center-image"/>  
<br>
するとポップアップが表示されるので、テストしたいAnddroid端末を選択して、「Install」をクリックすると、Android端末にアプリが自動でインストールされます。  
<img src="{{ './images/2024-01-09-10-14-05.png' }}" alt="image" width="250" class="center-image"/>  
<br>
Android端末側でもGooglePlayのアカウントの設定が必要かもしれません。私は設定済でした。  
  
<br>
あともう一つ設定が必要です。  
このままだとテスト課金でも実際に購入扱いされてしまうので、設定が必要です。  
Google Play Consoleにて、
「すべてのアプリ」  
「ライセンス　テスト」  
<img src="{{ './images/2024-01-19-13-55-06.png' }}" alt="image" width="200" class="center-image"/>  
  
以下のページが表示されますので、  
テスターを選択して、「変更を保存」をクリック。  
<img src="{{ './images/  .png' }}" alt="image" width="350" class="center-image"/>  
  
設定は以上だと思いますが、テスト課金設定は私の環境ではすぐに反映されませんでした。  
設定されてないので、暫く待つという情報もあったり。  
3時間後に再び試してみたところ、テスト課金ができるようになりました。  
<img src="{{ './images/2024-01-19-14-03-59.png' }}" alt="image" width="250" class="center-image"/>

<br>
記事としては以上です。  
Androidについては、内部テストアプリでないと課金テストができないし、  
内部テストの配布仕様が分かりにくし、  
すぐに試験できない仕様のようで。  

ということで記事化しました。  
  
<br>  

繰り返しとなりますが、私の環境用なので、参照程度にしてください。  
  
以上です！  
  
