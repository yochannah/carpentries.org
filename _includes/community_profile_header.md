{% if role[0].starts_with_vowel %}
{% assign article = "an" %}
{% else %}
{% assign article = "a" %}
{% endif %}

<p>{{ role[0].description }}</p>


{% if role[0].website_link %}
<p>Read more about our {{ role[0].name }} on  <a href="{{ role[0].website_link }}">The Carpentries website</a>. 
{% endif %}

{% if role[0].handbook_link %}
Check out our resources for {{ role[0].name }} in our <a href="{{ role[0].handbook_link }}">Handbook</a>.  </p>
{% endif %}

<p>This page lists {{ role[0].name }} who have consented to appear on our website. If you are {{ article }}
  {{ role[0].name_singular }} who is not listed here but would like to be, please 
  <a href="{{site.amy_landing}}">update your profile in AMY (our internal database)</a> and agree to make
  your profile public. Log in with GitHub and save your changes. If you have difficulty logging in, please 
  <a href="mailto:{{site.contact}}">email us</a>. <a href="/community-member-profile-faq/">Read more about how these profiles are published</a>.
