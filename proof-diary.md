---
title: Proof Diary
layout: page
permalink: /proof-diary/
---

{% assign coll = site.collections | where: "label", "proof-diary" | first %}
{% if coll and coll.docs and coll.docs.size > 0 %}
<ul>
  {% assign posts = coll.docs | sort: "date" | reverse %}
  {% for p in posts %}
    <li>
      <a href="{{ p.url | relative_url }}">{{ p.title | default: p.path }}</a>
      {% if p.date %} — <small>{{ p.date | date: "%Y-%m-%d" }}</small>{% endif %}
    </li>
  {% endfor %}
</ul>
{% else %}
<p>No entries yet.</p>
{% endif %}

<hr>
<h3>Debug: collection URLs</h3>
<ul>
{% assign coll = site.collections | where: "label", "proof-diary" | first %}
{% for p in coll.docs %}
  <li><code>{{ p.path }}</code> → <code>{{ p.url | relative_url }}</code></li>
{% endfor %}
</ul>
