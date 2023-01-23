---
layout: tag
toc: false
permalink: /Events
title: The Sierra Caerulea Conflict
header:
  overlay_color: "#000"
  overlay_filter: "0.25"
  overlay_image: /assets/images/banners/Heresy_NightFightTanks.png
taxonomy: events
entries_layout: grid
classes: wide
---

## Next Event
{% assign curDate = site.time | date: '%s' %}
{% for post in site.posts reversed %}
    {% if post.tags contains "events" %}
        {% assign postStartDate = post.event_date | date: '%s' %}
        {% if postStartDate >= curDate %}
            <img src={{post.header.overlay_image}} width="80%">

            [{{ post.title }}]({{ post.permalink }})
            
            {{ post.event_date | date: '%a, %b %d, %Y'}}

            {% break %}
        {% endif %}
    {% endif %}
{% endfor %}


## Compendium