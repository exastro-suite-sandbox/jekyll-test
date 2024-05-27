---
layout: common
---

## FAQ

{% assign doclist = site.pages | sort: 'url' %}


{% for faq in site.data.faq %}

<style>
    .text p:first-child {
        margin-top: 0!important;
        margin-left: 0!important;
    }
</style>

<h3 style="margin-bottom: 32px">{{ faq.name }}</h3>

<div class="faqBody">

<ul>

    {% for doc in doclist %}
        {% if doc.url contains faq.category %}

<li style="list-style: none; padding:0; margin:0;">
    <dl id="">
        <dt class="q"><span class="mark">Q</span><span class="text">{{doc.title}}</span></dt>
        <dd class="a" style="display:block;">
            <span class="mark">A</span><span class="text">
{{doc.content}}
            </span>
            <div class="permalink"><a href="{{site.url}}{{site.repository}}{{doc.url}}">Permalink</a></div>
        </dd>
    </dl>
</li>

        {% endif %}
    {% endfor %}
</ul>
</div>
{% endfor %}
