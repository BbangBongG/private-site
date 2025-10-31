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
      <a href="{{ p.url | relative_url }}">
        {{ p.title | markdownify | replace: '<p>', '' | replace: '</p>', '' }}
      </a>
      {% if p.date %} — <small>{{ p.date | date: "%Y-%m-%d" }}</small>{% endif %}
    </li>
  {% endfor %}
</ul>
{% else %}
<p>No entries yet.</p>
{% endif %}

<!-- MathJax for LaTeX in titles on this page -->
<script>
  window.MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$','$$'], ['\\[','\\]']]
    }
  };
</script>
<script id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
