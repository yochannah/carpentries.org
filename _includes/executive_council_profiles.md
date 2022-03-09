
{% for person in people_list %}

{% assign loopindex = forloop.index | modulo: 3 %}

{% if loopindex == 1 %}
<div class="row">
{% endif %}


<div class="medium-4 columns">
<div class="team-member anchor-offset" id="{{ person.github }}">
<img src="{{ site.filesurl }}/exec_council/{{ person.pic }}" class="img-responsive img-circle" alt="">

  <h3>{{ person.person_name }}</h3>

{% for t in person.term %}
<i>{{ t.type }} {{ t.start_year }}</i>
{% if forloop.last %}<br>{% else %}&#8226;{% endif %}
{% endfor %}


{% for role in person.roles %}{% if role.role != "Member" %}   
{{ role.committee }} {{role.role }}<br>
{% endif %} {% endfor %}


  <ul class="list-inline social-buttons">
      {% if person.twitter %}<li> <a href="https://twitter.com/{{ person.twitter }}"> <i class="fab fa-twitter" title="Twitter"></i> </a> </li> {% endif %}
      {% if person.github %}<li> <a href="https://github.com/{{ person.github }}"> <i class="fab fa-github" title="GitHub"></i> </a> </li> {% endif %}
      {% if person.orcid %}<li> <a href="https://orcid.org/{{ person.orcid }}"> <i class="fab fa-orcid" title="ORCID"></i> </a> </li> {% endif %}
      {% if person.url and person.url != "" %}<li> <a href="{{ person.url }}"> <i class="fas fa-link" title="Website"></i> </a> </li> {% endif %}
  </ul>
  {% unless person.country == "" %}
  <img width="64" src="/files/flags/{{ person.country | downcase }}.svg" alt={{person.country}} title={{person.country}} />
  {% endunless %}
</div>
</div>


{% if loopindex == 0 %}
</div>
{% endif %}
{% endfor %}



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