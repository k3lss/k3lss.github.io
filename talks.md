---
layout: single
permalink: /talks/
title: "Talks & Posters"
author_profile: true
classes: wide
---

<style>
  .talk {
    display: flex;
    gap: 1.5em;
    align-items: flex-start;
    margin-bottom: 2em;
  }
  .talk__thumb {
    flex: 0 0 180px;
  }
  .talk__thumb img {
    width: 100%;
    border-radius: 4px;
  }
  .talk__body h3 {
    margin-top: 0;
  }
  .talk__type {
    display: inline-block;
    padding: 0.1em 0.6em;
    margin-bottom: 0.4em;
    border-radius: 4px;
    border: 1px solid currentColor;
    font-size: 0.75em;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }
  @media (max-width: 600px) {
    .talk {
      flex-direction: column;
    }
    .talk__thumb {
      flex-basis: auto;
      max-width: 240px;
    }
  }
</style>

{% comment %}
  Entries are read from _data/talks.yml.
{% endcomment %}
{% assign talks_by_year = site.data.talks | sort: "date" | reverse | group_by_exp: "talk", "talk.date | date: '%Y'" %}

{% for year in talks_by_year %}
<h2 class="archive__subtitle">{{ year.name }}</h2>
{% for talk in year.items %}
<div class="talk">
  {% if talk.thumbnail %}
  <a class="talk__thumb" href="{{ talk.pdf | default: talk.thumbnail | relative_url }}">
    <img src="{{ talk.thumbnail | relative_url }}" alt="{{ talk.type }}: {{ talk.title }}" loading="lazy">
  </a>
  {% endif %}
  <div class="talk__body">
    <span class="talk__type">{{ talk.type }}</span>
    <h3>{{ talk.title }}</h3>
    {% if talk.authors %}<p>{{ talk.authors }}</p>{% endif %}
    <p>
      {% if talk.event_url %}<a href="{{ talk.event_url }}"><em>{{ talk.event }}</em></a>{% else %}<em>{{ talk.event }}</em>{% endif %},
      {{ talk.location }}. {% if talk.dates %}{{ talk.dates }}{% else %}{{ talk.date | date: "%B %Y" }}{% endif %}.
    </p>
    {% if talk.pdf %}
    <p><a href="{{ talk.pdf | relative_url }}"><i class="far fa-fw fa-file-pdf" aria-hidden="true"></i> {% if talk.type == "Poster" %}Poster{% else %}Slides{% endif %} (PDF)</a></p>
    {% endif %}
  </div>
</div>
{% endfor %}
{% endfor %}
