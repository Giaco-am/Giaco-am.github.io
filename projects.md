---
layout: default
title: projects
permalink: /projects/
---

# projects

Below are selected documents and work. PDF links open directly.

## documents

<ul>
{% assign doc_files = site.static_files | where: "extname", ".pdf" %}
{% for myfile in doc_files %}
  {% if myfile.path contains "/docs/" %}
    {% assign display_name = myfile.name | remove: myfile.extname %}
    <li><a href="{{ myfile.path | relative_url }}">{{ display_name }}</a></li>
  {% endif %}
{% endfor %}
</ul>