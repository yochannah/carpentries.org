---
layout: page-fullwidth
title: "Our Current Member Organisations"
permalink: "/members/"
---

{% include lazyload.html %}
{% assign platinum_members = site.data.members | where: "variant", "platinum" | sort: "name" %}
{% assign gold_members = site.data.members | where: "variant", "gold" | sort: "name" %}
{% assign silver_members = site.data.members | where: "variant", "silver" | sort: "name" %}
{% assign bronze_members = site.data.members | where: "variant", "bronze" | sort: "name" %}

A Member Organisation is an organisation that has made a financial commitment to
the growth and sustainability of The Carpentries and is building local capacity for training. See more on [becoming a Member Organisation]({% link pages/membership.md %}).

### Platinum Member Organisations

<ul>
{% for member in platinum_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>       {% if member.country == "" %}
     <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
     {% else %}
     <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
     {% endif %}   </li>{% endfor %}
</ul>


### Gold Member Organisations

<ul>
{% for member in gold_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>      {% if member.country == "" %}
     <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
     {% else %}
     <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
     {% endif %}   </li>{% endfor %}
</ul>


### Silver Member Organisations

<ul>
{% for member in silver_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>       {% if member.country == "" %}
     <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
     {% else %}
     <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
     {% endif %}  </li>{% endfor %}
</ul>


### Bronze Member Organisations

<ul>
{% for member in bronze_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>       {% if member.country == "" %}
     <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
     {% else %}
     <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
     {% endif %}  </li>{% endfor %}
</ul>

