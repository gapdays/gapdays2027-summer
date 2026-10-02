---
layout: page
title: Participants
participants:
  - {name: Pete Gautam, affiliation: "University of Manchester, UK"}
  - {name: Martin van Beek, affiliation: "University of Manchester, UK"}
  - {name: Ruth Hoffmann, affiliation: "University of St Andrews, Scotland"}
  - {name: Max Horn, affiliation: "RPTU University Kaiserslautern-Landau, Germany"}
---

<ol>{% assign participants = page.participants | sort: "name" %}
{% for p in participants %}
  <li>
    <strong{% if p.online == true %} style="color: blue; font-style: italic"{% endif %}>{{ p.name }}</strong>
    {% if p.affiliation != null %} ({{ p.affiliation }}){% endif %}
    {% if p.links != null %}
        {% for item in p.links %}
            <a href="{{ item[1] }}">({{ item[0] }})</a>
        {% endfor %}
    {% endif %}
    <br/>
      {% if p.talk != null %} Talk: {{ p.talk }}{% endif %}
  </li>
{% endfor %}
</ol>

{% if site.data.feedback.size > 0 %}

<ul>
{% for p in site.data.feedback %}
  <li>
    <strong>{{ p.name }}</strong>
    {% if p.package != null %} (author of {{ p.package }}){% endif %}
    <br/>
    {% if p.feedback != null %} {{ p.feedback }}{% endif %}
  </li>
{% endfor %}
</ul>

{% endif %}
