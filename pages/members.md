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

View our [current member sites on a map]({% link pages/members-map.html %}).

### Platinum Member Organisations

<ul>
{% for member in platinum_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>
    {% if member.country == "" %}
        <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
    {% else %}
        <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
    {% endif %}
</li>
{% endfor %}
</ul>


### Gold Member Organisations

<ul>
{% for member in gold_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>
    {% if member.country == "" %}
        <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
    {% else %}
        <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
    {% endif %}
</li>
{% endfor %}
</ul>


### Silver Member Organisations

<ul>
{% for member in silver_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>
    {% if member.country == "" %}
        <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
    {% else %}
        <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
    {% endif %}
</li>
{% endfor %}
</ul>

### Bronze Member Organisations

<ul>
{% for member in bronze_members %}
<li>
    <a href = "https://{{ member.domain }}">{{ member.name }}</a>
    {% if member.country == "" %}
        <img width="24" src="/files/flags/w3.svg" alt={{member.country}} title={{member.country}} />
    {% else %}
        <img width="24" src="/files/flags/{{ member.country | downcase }}.svg" alt={{member.country}} title={{member.country}} />
    {% endif %}
</li>
{% endfor %}
</ul>

<script>
    var images = document.getElementsByTagName('img')
    // Start loop at 1. Hacky way to avoid the banner image.
    for (let i=1; i < images.length; i++) {
        var regionNames = new Intl.DisplayNames(['en'], {type: 'region'});
        fullName = regionNames.of(images[i].title);
        images[i].title = fullName;
        images[i].alt = fullName;
    }
</script>

