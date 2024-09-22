---
layout: default
title: docs
permalink: /docs/
---

<style>
  /* Add any additional styles for the Docs page here */
</style>

# Documents

Below is a list of available documents:

<ul>
{% assign doc_files = site.static_files | where: "extname", ".pdf" %}
{% for myfile in doc_files %}
  {% if myfile.path contains "/docs/" %}
    <li><a href="{{ myfile.path | relative_url }}">{{ myfile.name }}</a></li>
  {% endif %}
{% endfor %}
</ul>
