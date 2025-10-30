---
layout: default
title: Proof Diary
permalink: /proof-diary/
---

<h1>Proof Diary</h1>

<ul>
{% assign entries = site.proof-diary | sort: "date" | reverse %}
{% for entry in entries %}
  <li>
    <a href="{{ entry.url | relative_url }}">{{ entry.title }}</a>
    <small>({{ entry.date | date: "%Y-%m-%d" }})</small>
  </li>
{% endfor %}
</ul>
