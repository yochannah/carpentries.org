
<img data-src="{{ person.pic }}" width="128" height="128" class="img-responsive img-circle lazyload" alt="GitHub profile photo of {{ person.name }}" />
<h3>{{ person.name }}</h3>
<ul class="list-inline social-buttons">

    {% for network in person.social %}
    <li>
        <a href="{{ network.url }}">
            <i class="{{ network.icon }}"></i>
        </a>
    </li>
    {% endfor %}
</ul>

