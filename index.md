---
layout: default
---

__Welcome to Slow Tech Brisbane!__ We are an eclectic group of people based in Brisbane, Australia, who share a belief that general participation in the proliferation of computers is the key to avoiding a digital future rife with misuse and misappropriation of our electronic resources by governments, businesses, and other malicious individuals.

[Learn more...](/about/)

Most of the conversation occurs in a Matrix room
[here](https://matrix.to/#/#slowtechbne:matrix.org). Feel free to join on a
client that supports encryption (like [Riot](https://riot.im)). We plan to set
up a mailing list soon, too.

<!---
#### Recent news

{% for item in site.news reversed limit:2 %}
  {{ item.date }} --- <strong>{{ item.title }}</strong>

  <div class="index-news">
    {{ item.content }}
  </div>
{% endfor %}
--->

{% if site.data.events %}

#### [Upcoming events](/events/)

<div id="events">
{% for event in site.data.events %}
  {% capture nowunix %}{{ site.time | date: '%s' }}{% endcapture %}
  {% capture eventunix %}{{ event.date | date: '%s' }}{% endcapture %}
  {% if eventunix > nowunix %}
  <div class="event">
    <strong>{{ event.title }}</strong>{% if event.subtitle %} | {{ event.subtitle }}{% endif %}
    <div class="meta">
      <span class="time">{{ event.time }}, {{ event.date | date: "%d %B, %Y"}}</span>
    <span class="separator">|</span>
    {{ event.location }} <a href="https://www.openstreetmap.org/{{ event.osm }}"><i class="fa fa-location-arrow"></i></a>
    </div>
    <div class="description">{{ event.description | markdownify }}</div>
  </div>
  {% endif %}
{% endfor %}
</div>

##### [More events](/events/)

{% else %}
{% endif %}
