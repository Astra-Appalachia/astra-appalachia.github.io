---
layout: tag
toc: false
permalink: /Events
title: Our Events
header:
  overlay_color: "#000"
  overlay_filter: "0.25"
  overlay_image: /assets/images/banners/Heresy_NightFightTanks.png
taxonomy: events
entries_layout: grid
classes: wide
---
{% assign curDate = site.time | date: "%s" %}

{% for post in site.posts reversed %}
    {% if post.tags contains "events" %}
        {% assign postStartDate = post.event_date | date: "%s" %}
        {% if postStartDate >= curDate %}
            {% assign nextEvent = post %}
            {% break %}
        {% endif %}
    {% endif %}
{% endfor %}

## Next Event

[{{ nextEvent.title }}]({{ nextEvent.permalink }})
{{ nextEvent.event_date | date: "%a, %b %d, %Y"}}

## Compendium