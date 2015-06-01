---
layout: default
---

__Welcome to Slow Tech Brisbane!__ We are an eclectic group of people based in Brisbane, Australia, who share a belief that general participation in the proliferation of computers is the key to avoiding a digital future rife with misuse and misappropriation of our electronic resources by governments, businesses, and other malicious individuals.

[Learn more...](/about/)

#### Recent news

{% for item in site.news limit:5 %}
  {{ item.date | date: '%D' }} --- <strong>{{ item.title }}</strong>

  <div class="index-news">
    {{ item.content }}
  </div>

{% endfor %}

{% if site.data.events.size < 0 %}

#### [Upcoming events](/events/)

<div id="events">
{% for event in site.data.events %}
  {% capture nowunix %}{{ site.time | date: '%s' }}{% endcapture %}
  {% capture eventunix %}{{ event.date | date: '%s' }}{% endcapture %}
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
</div>

##### [Past events](events#past)

{% else %}

{% endif %}
