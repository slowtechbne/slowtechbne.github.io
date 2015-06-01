---
layout: default
---

### Welcome to Slow Tech Brisbane!



#### Recent news

#### [Upcoming events](/events/)

<div id="events">
{% for event in site.data.events %}
  {% capture nowunix %}{{ site.date | date: '%s' }}{% endcapture %}
  {% capture eventunix%}{{ event.date | date: '%s' }}{% endcapture %}
  {% if eventunix > nowunix %}
  <div class="event">
    <strong>{{ event.title }}</strong> | {{ event.subtitle }}
    <div class="meta">
      <span class="time">{{ event.time }}, {{ event.date | date: "%d %B, %Y"}}</span>
    <span class="separator">|</span>
    {{ event.location }} <a href="https://www.openstreetmap.org/{{ event.osm }}"><span class="glyphicon glyphicon-map-marker"></span></a>
    </div>
    <div class="description">{{ event.description | markdownify }}</div>
  {% endif %}
{% endfor %}
</div>
