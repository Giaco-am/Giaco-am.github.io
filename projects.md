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
  {% if myfile.path contains "/assets/docs/" %}
    {% assign display_name = myfile.name | remove: myfile.extname | replace: '-', ' ' %}
    <li><a href="{{ myfile.path | relative_url }}">{{ display_name }}</a></li>
  {% endif %}
{% endfor %}
</ul>

## papers

<ul>
  <li>
    <a href="https://arxiv.org/pdf/2506.17040">Stretching Beyond the Obvious: A Gradient-Free Framework to Unveil the Hidden Landscape of Visual Invariance</a>
    <div class="muted">Tausani, Muratore, Talbot, Amerio, Kreiman, Zoccolan</div>
  </li>
</ul>

## repositories

<ul>
{% for item in site.data.repos %}
  <li>
    <a href="https://github.com/{{ item.repo }}">{{ item.title }}</a>
    {% if item.description %}<div class="muted">{{ item.description }}</div>{% endif %}
    {% if item.tags %}<div class="muted">{{ item.tags | join: " · " }}</div>{% endif %}
  </li>
{% endfor %}
</ul>