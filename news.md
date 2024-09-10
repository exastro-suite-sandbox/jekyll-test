---
layout: common
---

## NEWS

{% assign i = 0 %}

<ul>
{% for newsData in site.data.news %}
    {% for newsItem in newsData[1] %}
        {% if i == 4 %}{% break %}{% endif %}
<li id="{{ newsItem.id }}">
    <dl>
        {% if newsItem.image %}<dt class="image">
            <a href="{{ newsItem.url }}" class="touch" target="_blank" rel="noopener">
                <img src="{{ newsItem.image | relative_url }}" alt="{{ newsItem.title | xml_escape }}">
            </a>
        </dt>{% endif %}
        {% if newsItem.videoId %}<dt class="newsRoomVideoWrap">
            <span class="newsRoomVideo youtubeEmbed" data-embed-id="{{ newsItem.videoId }}"><span id="{{ newsItem.videoId }}"></span></span>
        </dt>{% endif %}
        <dd class="title">
            <a href="{{ newsItem.url }}" target="_blank" rel="noopener">
                <span class="mainTitle">{{ newsItem.title | xml_escape }} <i class="fas fa-external-link-alt"></i></span>
                {% if newsItem.subTitle %}<span class="subTitle">{{ newsItem.subTitle | xml_escape }}</span>{% endif %}
            </a>
        </dd>
        <dd class="meta">
            <div class="media">
                <i class="far fa-sticky-note"></i> {{ newsItem.media }}
            </div>
            <div class="date">
                <i class="far fa-clock"></i> <time datetime="{{ newsItem.date }}">{{ newsItem.date }}</time>
            </div>
        </dd>
        {% if newsItem.document %}{% for documentItem in newsItem.document %}
        <dd class="document">
            <a href="{{ documentItem.url }}" target="_blank">
                <i class="fas fa-video"></i> {{ documentItem.title }} <i class="fas fa-external-link-alt">{% if documentItem.note %}<br>{{ documentItem.note }}{% endif %}</i>
            </a>
        </dd>
        {% endfor %}{% endif %}
        {% capture i %}{{ i | plus: 1 }}{% endcapture %}
    </dl>
</li>
    {% endfor %}
{% endfor %}
</ul>



## Date

{{ "2024-01-01" | date: "%Y%m%d" }}


