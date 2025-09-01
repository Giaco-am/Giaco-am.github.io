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
    {% assign description = nil %}
    {% if myfile.name == "eu-ai-essay.pdf" %}
      {% assign description = "EU AI Act transparency centers on risk/compliance, not technical interpretability. In this essay I propose 'Interpretability-as-Infrastructure' embedding mechanistic interpretability artifacts (e.g., attribution graphs) in documentation to link liability to interpretability and make accountability enforceable." %}
    {% elsif myfile.name == "periodo-e-momenti.pdf" %}
      {% assign description = "A collection of my poems, written in Italian." %}
    {% elsif myfile.name == "thesis.pdf" %}
      {% assign description = "EEG data correlation analysis via intrinsic dimension estimation; predicts functional connectivity from intrinsic dimensionality of coupled EEG signals. Written in Italian" %}
    {% endif %}
    <li>
      <a href="{{ myfile.path | relative_url }}">{{ display_name }}</a>
      {% if description %}<div class="muted">{{ description }}</div>{% endif %}
    </li>
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