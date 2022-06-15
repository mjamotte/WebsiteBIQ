---
title: "BIQ - Events"
layout: gridlay
excerpt: "BIQ -- Events"
sitemap: false
permalink: /events/
---


# Events

## Next events

{% assign number_printed = 0 %}
{% for event in site.data.events %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ event.title }}  </pubtit> 
  <p>{{ event.headline }}</p>
  <img src="{{ site.url }}{{ site.baseurl }}/images/logopic/{{ event.image }}" class="img-responsive" width="25%" style="float: left" />
  <p>{{ event.description }}</p>
  <p><b> [{{ event.date }}]</p>
  <p><em> {{ event.description_authors }} <a href="{{event.authors_page}}">{{ event.authors}}</a></em></p>
  <p><strong><a href="{{ event.link.url }}">{{ event.link.display }}</a></strong></p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

## Past events

{% assign number_printed = 0 %}
{% for past_event in site.data.past_events %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix" >
 <div class="well" style="background: #F5F5DC;;">
  <pubtit>{{ past_event.title }}  </pubtit> 
  <p>{{ past_event.headline }}</p>
  <img src="{{ site.url }}{{ site.baseurl }}/images/logopic/{{ past_event.image }}" class="img-responsive" width="25%" style="float: left" />
  <p>{{ past_event.description }}</p>
  <p><b> [{{ past_event.date }}]</p>
  <p><em> {{ past_event.description_authors }} <a href="{{past_event.authors_page}}">{{ past_event.authors }}</a></em></p>
  <p><strong><a href="{{ past_event.link.url }}">{{ past_event.link.display }}</a></strong></p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}