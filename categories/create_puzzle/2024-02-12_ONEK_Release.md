---
layout: post
title: "[ONE K]アプリ情報"
categories: [one_k]
tags: []
thumbnail: "./images/2024-01-29-00-03-52.png"
---

スマホアプリでリリースしている
「ONE K」
の情報となります。
  
<br>
  
同じ数字を合体させて、より大きな数字を目指していくゲームです。  

<iframe width="560" height="315" src="https://www.youtube.com/embed/ulyfyhqVzSI" frameborder="0" allowfullscreen></iframe>  
  
<br>
<hr>
<br>
  
## iOS
<!-- <img src="{{ './images/icon_ios.jpg' }}" alt="image" width="250" class="center-image"/> -->
  
<br>
  
## Android
<!-- <a class="post-link" href="https://play.google.com/store/apps/details?id=com.Combo.puzzle">
    <img src="{{ './images/icon_android.png' }}" alt="image" width="250" class="center-image"/>
</a> -->
  
<br>
<hr>
<br>

## ONE K アプリ情報
#### unityroom
###### タイトル
ONE K
<br>

###### 紹介文
2048風のパズルゲームです。  
「2」、「4」、「8」、「16」と数字が書かれたブロックが落ちてくるので、  
同じ数字のブロックを合体させてください！  
そのブロック数字が合計され大きな数字のブロックとなります。  
  
そうして「1024」(このアプリでは1Kと呼びます)を目指してください！  
  
キミは１Kに到達できるか！！！  
  
★☆★unityroomではスタンダードモードのみご利用いただけます。★☆★  
★☆★より面白いアドバンスモードはスマホ版をダウンロードしてください。★☆★  
<br>

###### 想定プレイ時間
3分程度  
<br>

###### 操作方法
■マウス操作
マウスでの操作の場合、落下させたり列をクリックしてください。
クリックした列にブロックがすぐに落下します。

■キーボード操作
キーボードの操作の場合、ブロックの左右は矢印キー「←」、「→」で行います。
「↓」を押すと、ブロックがいる列にすぐに落下します。

## ONE K 記事一覧
<ul class="post-list">
    {%- assign default_paths = site.pages | map: "path" -%}
    {%- assign page_paths = site.header_pages | default: default_paths | reverse -%}
    {%- for path in page_paths -%}
      <li>
        {%- assign my_page = site.pages | where: "path", path | first -%}
        
        {%- if my_page.title and my_page.title != "" -%}
            {%- if my_page.url contains "create_puzzle" -%}
                {%- assign date_format = site.minima.date_format | default: "%Y/%m/%d" -%}
                <span class="post-meta">{{ my_page.date | date: date_format }}</span>
                <h3>
                    <a class="post-link" href="{{ my_page.url | relative_url }}">
                        {% if my_page.thumbnail %}
                            {% assign filename = my_page.path | split: "/" | last %}
                            <img class="thumbnail" src="{{ my_page.thumbnail }}" alt="" />
                        {% endif %}
                        
                        {{ my_page.title | escape }}
                    </a>
                </h3>
                
            {% endif %}
        {%- endif -%}
      </li>
    {%- endfor -%}
  </ul>