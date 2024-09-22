
---
layout: default
title: Docs
permalink: /docs/
---

<style>
  /* Add any additional styles if needed */
</style>

# Documents

Here is a list of documents:

<ul>
{% for doc in site.static_files %}
  {% if doc.path contains '/docs/' %}
    <li><a href="{{ doc.path | relative_url }}">{{ doc.name }}</a></li>
  {% endif %}
{% endfor %}
</ul>




