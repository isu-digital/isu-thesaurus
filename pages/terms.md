---
title: Term List
layout: page
permalink: /terms.html
---

# Term List

Alphabetical list of terms, with links to each term's record. (This is just another way to view the information on the Browse page).

{% capture letters %}{% for item in site.data[site.metadata] %}{{ item.title | slice: 0 | capitalize }};{% endfor %}{% endcapture %}
{%- assign uniqueLetters = letters | split: ';' | uniq | sort -%}
{%- assign glossary = site.data[site.metadata] | sort: "title" -%}

<ul class="list-inline">
{% for letter in uniqueLetters %}
<li class="list-inline-item h2"><a href="#{{ letter }}">{{ letter }}</a></li>
{% endfor %}
</ul>
<hr>

<div>

{% for letter in uniqueLetters %}
<h2 class="pt-4" id="{{ letter }}">{{ letter }}</h2>

<dl id="glossary-list">
{% for item in glossary %}
{%- assign x = item.title | slice: 0 | capitalize -%}
{%- if x == letter -%}
    <dt class="glossary-def"><a href="{{ '/items/' | append: item.objectid | append: '.html' | relative_url }}">
    {{ item.title }}</a></dt> 
    <dd>{{ item.definition }}</dd>
{%- endif -%}
{%- endfor -%}
</dl>

{%- endfor -%}
</div>
