# Kyopro Encyclopedia of 典型テク (α版)

このページでは、通常は「アルゴリズム」とは呼ばれないようなものたちを紹介する。通常のアルゴリズムたちについては [Kyopro Encyclopedia of Algorithms](../) を参照のこと。

<hr>

<dl>
{% assign sorted_tenkeis = site.tenkeis | sort: "title" %}
{% for entry in sorted_tenkeis %}
   {% assign entry_id = entry.url | split: "/" | last | split: "." | first %}
   {% if entry.draft %}
       <dt id="{{ entry_id }}">
            {{ entry.title }}
            <a href="#{{ entry_id }}" class="draft-link">{% octicon link height:16 %}</a>
            {% for url in entry.draft_urls %} <a href="{{ url }}" class="link-external">{% octicon link-external height:16 %}</a>{% endfor %}
       </dt>
       <dd>{{ entry.description }}</dd>
   {% else %}
       <dt><a href="{{ entry.url | relative_url }}">{{ entry.title }}</a></dt>
       <dd>{{ entry.description }}</dd>
   {% endif %}
{% endfor %}
</dl>

<div class="footer-links">
    <a href="{{ "/" | relative_url }}">アルゴリズム版</a> /
    <a href="{{ site.github.repository_url }}">GitHub repository</a>
</div>
