---
title: Vocabularies
layout: page
permalink: /vocab/
---

# Vocabulary List

Alphabetical list of vocabularies, which link to pages about each vocabulary.

{% capture letters %}{% for item in site.data.vocabulary-sources %}{{ item.title | slice: 0 | capitalize }};{% endfor %}{% endcapture %}
{%- assign uniqueLetters = letters | split: ';' | uniq | sort -%}
{%- assign glossary = site.data.vocabulary-sources | sort: "title" -%}

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
    <dt class="glossary-def"><a href="{{ '/vocab/' | append: item.objectid | append: '.html' | relative_url }}">
    {{ item.title }}</a></dt> 
    <dd>{{ item.description }}</dd>
{%- endif -%}
{%- endfor -%}
</dl>

{%- endfor -%}
</div>
