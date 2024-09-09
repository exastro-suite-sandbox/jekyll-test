---
layout: common
---

## NEWS

<ul>
{% for newsYearList in site.data.news %}
    {% for item in newsYearList[1] %}

<li id="news20230222">
    <dl>
        <dt class="image"><a href="{{ item.url }}" class="touch" target="_blank" rel="noopener"><img src="{{ item.image | relative_url }}" alt="{{ item.title }}"></a></dt>
        <dd class="title"><a href="{{ item.url }}" target="_blank" rel="noopener">{{ item.title }} <i class="fas fa-external-link-alt"></i></a></dd>
        <dd class="meta"><div class="media"><i class="far fa-sticky-note"></i> {{ item.publication }}</div><div class="date"><i class="far fa-clock"></i> <time datetime="{{ item.date }}">{{ item.date }}</time></div></dd>
    </dl>
</li>

    {% endfor %}
{% endfor %}
</ul>


