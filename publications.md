---
layout: single
permalink: /publications/
title: "Publications"
author_profile: true
classes: wide
---

You can also find my publications on
[NASA ADS](https://ui.adsabs.harvard.edu/search/q=orcid%3A0009-0000-8796-271X&sort=date%20desc),
[arXiv](https://arxiv.org/a/merino_c_1) and
[Google Scholar](https://scholar.google.com/citations?user=ZoPEG8EAAAAJ&hl=es).

{% comment %}
  Entries are read from _data/publications.yml.
{% endcomment %}
{% assign papers_by_year = site.data.publications.papers | group_by: "year" %}

{% for year in papers_by_year %}
<h2 class="archive__subtitle">{{ year.name }}</h2>
<ul>
{% for paper in year.items %}
  {% include publication.html paper=paper %}
{% endfor %}
</ul>
{% endfor %}
