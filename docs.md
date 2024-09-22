---
layout: default
title: documents
permalink: /docs/
---

<style>
  /* Add any additional styles for the Docs page here */
</style>

# docs

available documents:

<ul>
{% assign doc_files = site.static_files | where: "extname", ".pdf" %}
{% for myfile in doc_files %}
  {% if myfile.path contains "/docs/" %}
    {% assign display_name = myfile.name | remove: myfile.extname %}
    <li><a href="{{ myfile.path | relative_url }}">{{ display_name }}</a></li>
  {% endif %}
{% endfor %}
</ul>

<br>
[back](/)