---
layout: post
title: "「ゲーム攻略」の記事一覧"
categories: [review_game]
tags: []
thumbnail: ""
---

<div class="home">
  {%- assign default_paths = site.pages | map: "path" -%}
  {%- assign page_paths = default_paths | reverse -%}
  {% assign current_url = page.url %}

  <ul class="post-list">
    {%- for path in page_paths -%}
      <li>
        {%- assign my_page = site.pages | where: "path", path | first -%}
        {%- if my_page.title and my_page.title != "" and my_page.categories == page.categories and my_page.url != current_url -%}

          {% assign url_parts = my_page.url | split: '/' %}
          {% assign last_two_parts = my_page.url | split: '/' | slice: -2, 2 | join: '/' %}

          <a  href="{{ my_page.url | relative_url }}">
            {% if my_page.thumbnail != "" %}
              {% if last_two_parts contains 'review_game' %}
                <img class="thumbnail" src="{{ my_page.thumbnail }}" alt="" />
              {% else %}
                <img class="thumbnail" src="{{last_two_parts}}/{{ my_page.thumbnail }}" alt="" />
              {% endif %}
            {% endif %}
            
            {{ my_page.title | escape }}
          </a>
        
        {%- endif -%}
      </li>
    {%- endfor -%}
  </ul>
</div>
