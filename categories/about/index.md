---
layout: post
title: "「このブログについて」の記事一覧"
categories: [about]
tags: []
thumbnail: ""
---

<div class="home">
  {%- assign pages_with_sort_key = site.pages -%}
  {%- assign map_pages = pages_with_sort_key | map: "last_modified_at" | compact-%}
  {%- assign sorted_pages = map_pages | sort | reverse -%}

  {%- assign default_paths = site.pages | map: "path" -%}
  {%- assign page_paths = default_paths | reverse -%}
  {% assign current_url = page.url %}
  

  <ul class="post-list">
    {%- for path in page_paths -%}
      <li>
        {%- assign my_page = site.pages | where: "path", path | first -%}
        {%- if my_page.title and my_page.title != "" and my_page.categories contains "about" and my_page.url != current_url -%}
          <a  href="{{ my_page.url | relative_url }}">
            {% if my_page.thumbnail != "" %}
              <img class="thumbnail" src="{{ my_page.thumbnail }}" alt="" />
            {% endif %}
            
            {{ my_page.title | escape }}
          </a>
        
        {%- endif -%}
      </li>
    {%- endfor -%}
  </ul>
</div>
