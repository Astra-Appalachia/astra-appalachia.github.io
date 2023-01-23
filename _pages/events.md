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
---
<script async type="module" src="https://embed.styledcalendar.com/assets/parent-window.js"></script>

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

![image-center]({{ nextEvent.header.overlay_image }}){: .align-center}

[{{ nextEvent.title }}]({{ nextEvent.permalink }})
{: .text-center}

Join us on {{ nextEvent.event_date | date: "%a, %b %d, %Y"}}
{: .text-center}

```
{{ nextEvent.excerpt }}
```

--------

## Event Calender 
<iframe src="https://embed.styledcalendar.com/#7NlDuONV4yIlsbiSGL2H" title="Styled Calendar" class="styled-calendar-container" style="width: 100%; border: none;" data-cy="calendar-embed-iframe"></iframe>
{: .text-center}

## Reverse-Chronological Compendium